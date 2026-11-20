<script lang="ts">
	import { onMount } from 'svelte';

	const vertexShader = `#version 300 es
in vec2 position;
void main() {
	gl_Position = vec4(position, 0.0, 1.0);
}`;

	const fragmentShader = `#version 300 es
precision highp float;

uniform vec3 iResolution;
uniform float iTime;
out vec4 outColor;

float rand(vec2 co){
    return fract(sin(dot(co, vec2(12.9898, 78.233))) * 43758.5453);
}

vec3 mod289(vec3 x) { return x - floor(x * (1.0 / 289.0)) * 289.0; }
vec4 mod289(vec4 x) { return x - floor(x * (1.0 / 289.0)) * 289.0; }
vec4 permute(vec4 x){ return mod289(((x*34.0)+1.0)*x); }
vec4 taylorInvSqrt(vec4 r){ return 1.79284291400159 - 0.85373472095314 * r; }

float snoise(vec3 v)
{
  const vec2  C = vec2(1.0/6.0, 1.0/3.0) ;
  const vec4  D = vec4(0.0, 0.5, 1.0, 2.0);

  vec3 i  = floor(v + dot(v, C.yyy) );
  vec3 x0 =   v - i + dot(i, C.xxx) ;

  vec3 g = step(x0.yzx, x0.xyz);
  vec3 l = 1.0 - g;
  vec3 i1 = min( g.xyz, l.zxy );
  vec3 i2 = max( g.xyz, l.zxy );

  vec3 x1 = x0 - i1 + C.xxx;
  vec3 x2 = x0 - i2 + C.yyy;
  vec3 x3 = x0 - D.yyy;

  i = mod289(i);
  vec4 p = permute( permute( permute(
             i.z + vec4(0.0, i1.z, i2.z, 1.0 ))
           + i.y + vec4(0.0, i1.y, i2.y, 1.0 ))
           + i.x + vec4(0.0, i1.x, i2.x, 1.0 ));

  float n_ = 0.142857142857;
  vec3  ns = n_ * D.wyz - D.xzx;

  vec4 j = p - 49.0 * floor(p * ns.z * ns.z);

  vec4 x_ = floor(j * ns.z);
  vec4 y_ = floor(j - 7.0 * x_ );

  vec4 x = x_ *ns.x + ns.yyyy;
  vec4 y = y_ *ns.x + ns.yyyy;
  vec4 h = 1.0 - abs(x) - abs(y);

  vec4 b0 = vec4( x.xy, y.xy );
  vec4 b1 = vec4( x.zw, y.zw );

  vec4 s0 = floor(b0)*2.0 + 1.0;
  vec4 s1 = floor(b1)*2.0 + 1.0;
  vec4 sh = -step(h, vec4(0.0));

  vec4 a0 = b0.xzyw + s0.xzyw*sh.xxyy ;
  vec4 a1 = b1.xzyw + s1.xzyw*sh.zzww ;

  vec3 p0 = vec3(a0.xy,h.x);
  vec3 p1 = vec3(a0.zw,h.y);
  vec3 p2 = vec3(a1.xy,h.z);
  vec3 p3 = vec3(a1.zw,h.w);

  vec4 norm = taylorInvSqrt(vec4(dot(p0,p0), dot(p1,p1), dot(p2, p2), dot(p3,p3)));
  p0 *= norm.x; p1 *= norm.y; p2 *= norm.z; p3 *= norm.w;

  vec4 m = max(0.6 - vec4(dot(x0,x0), dot(x1,x1), dot(x2,x2), dot(x3,x3)), 0.0);
  m = m * m;
  return 42.0 * dot( m*m, vec4( dot(p0,x0), dot(p1,x1),
                                dot(p2,x2), dot(p3,x3) ) );
}

const vec3  BACKGROUND   = vec3(1.0);
const float GRAIN        = 0.05;
const bool  SHOW_GRID    = true;
const float COLOUR_SPEED = 0.15;
const float FLOW_SPEED   = 0.03;
const float BAND_WIDTH   = 1.0;
const float BAND_PERIOD  = 20.0;
const float SATURATION   = 0.45; // 1 = full chroma, 0 = grey
const float PASTEL       = 0.5;  // how far each colour is mixed toward white

const float STEPS  = 200.;
const float CUTOFF = 0.;
const vec2  OFFSET = vec2(0.1,0.1);

vec3 palette(float x){
    return 0.5 + 0.5 * cos(6.28318530718 * (x + vec3(0.0, 0.33, 0.67)));
}

float getNoise(vec2 uv, float t){
    float SCALE = 2.0;
    float noise = snoise( vec3(uv.x*SCALE + t, uv.y*SCALE + t , 0));

    SCALE = 6.0;
    noise += snoise( vec3(uv.x*SCALE + t, uv.y*SCALE , 0))* 0.2 ;

    noise = (noise/2. + 0.5);
    return noise;
}

float getDepth(float n){
    float d = (n - CUTOFF) / (1. - CUTOFF);
    d = floor(d*STEPS)/STEPS;
    return d;
}

void mainImage( out vec4 fragColor, in vec2 fragCoord )
{
    vec2 uv = fragCoord.xy / iResolution.x;

    float curveFactor = pow(distance(fragCoord.xy, 0.5*iResolution.xy)*5./iResolution.x,4.);
    vec2 curveDirection = normalize(0.5*iResolution.xy-fragCoord.xy);
    vec2 curvedUV = (fragCoord.xy - curveFactor*curveDirection)/iResolution.x;

    float t  = iTime * 0.01;
    float tf = iTime * FLOW_SPEED;

    float noise = getNoise(curvedUV, t);
    float d     = getDepth(noise);

    float bandCoord = noise * STEPS;
    float bandVal   = mod(bandCoord, BAND_PERIOD);

    float aa = max(fwidth(bandCoord), 1e-5);

    float dist = min(bandVal, BAND_PERIOD - bandVal);

    float lineW = aa * BAND_WIDTH * 0.5;
    float v = 1.0 - smoothstep(lineW - aa*0.5, lineW + aa*0.5, dist);

    vec3 col = BACKGROUND;

    if(v > 0.001){
        float colourNoise = getNoise(curvedUV * 1.7 + vec2(tf*3.0, -tf*2.0) + 13.7, t * 1.3 + tf);

        float c = noise * 1.4
                + colourNoise * 0.7
                + d * 0.25
                + tf * 1.5
                + iTime * COLOUR_SPEED;

        vec3 bandCol = palette(c);
        bandCol = mix(vec3(dot(bandCol, vec3(0.299, 0.587, 0.114))), bandCol, SATURATION);
        bandCol = mix(vec3(1.0), bandCol, PASTEL);
        bandCol *= 0.7 + (fragCoord.y/iResolution.y * 0.3);
        bandCol += (rand(fragCoord.xy) - 0.5) * GRAIN;

        col = mix(col, bandCol, v);
    }

    if(SHOW_GRID){
        if(mod(curvedUV.x,0.1)<0.001) col += vec3(.3,.3,.3);
        if(mod(curvedUV.y+iResolution.y/iResolution.x*0.035,0.1)<0.001) col += vec3(.3,.3,.3);
    }

    fragColor = vec4(col,1.0);
}

void main() {
	mainImage(outColor, gl_FragCoord.xy);
}`;

	let canvas: HTMLCanvasElement | undefined = $state();
	onMount(() => {
		if (!canvas) return;
		const gl = canvas.getContext('webgl2', { antialias: false, alpha: false });
		if (!gl) return;

		const compile = (type: number, source: string) => {
			const shader = gl.createShader(type)!;
			gl.shaderSource(shader, source);
			gl.compileShader(shader);
			return shader;
		};

		const program = gl.createProgram()!;
		gl.attachShader(program, compile(gl.VERTEX_SHADER, vertexShader));
		gl.attachShader(program, compile(gl.FRAGMENT_SHADER, fragmentShader));
		gl.linkProgram(program);
		gl.useProgram(program);

		const buffer = gl.createBuffer();
		gl.bindBuffer(gl.ARRAY_BUFFER, buffer);
		gl.bufferData(
			gl.ARRAY_BUFFER,
			new Float32Array([-1, -1, 3, -1, -1, 3]),
			gl.STATIC_DRAW
		);
		const position = gl.getAttribLocation(program, 'position');
		gl.enableVertexAttribArray(position);
		gl.vertexAttribPointer(position, 2, gl.FLOAT, false, 0, 0);

		const resolution = gl.getUniformLocation(program, 'iResolution');
		const time = gl.getUniformLocation(program, 'iTime');

		const resize = () => {
			const dpr = Math.min(window.devicePixelRatio, 1.5);
			canvas!.width = Math.floor(window.innerWidth * dpr);
			canvas!.height = Math.floor(window.innerHeight * dpr);
			gl.viewport(0, 0, canvas!.width, canvas!.height);
			gl.uniform3f(resolution, canvas!.width, canvas!.height, 1);
		};
		resize();
		window.addEventListener('resize', resize);

		const reducedMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
		const start = performance.now();
		let frame = 0;

		const draw = () => {
			gl.uniform1f(time, (performance.now() - start) / 1000);
			gl.drawArrays(gl.TRIANGLES, 0, 3);
		};

		const loop = () => {
			draw();
			frame = requestAnimationFrame(loop);
		};

		if (reducedMotion) {
			draw();
		} else {
			loop();
			document.addEventListener('visibilitychange', onVisibility);
		}

		function onVisibility() {
			cancelAnimationFrame(frame);
			if (!document.hidden) loop();
		}

		return () => {
			cancelAnimationFrame(frame);
			document.removeEventListener('visibilitychange', onVisibility);
			window.removeEventListener('resize', resize);
		};
	});
</script>

<canvas bind:this={canvas} class="pointer-events-none absolute inset-0 h-full w-full" aria-hidden="true"></canvas>
