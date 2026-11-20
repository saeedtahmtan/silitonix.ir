<script lang="ts">
	let { class: className = '' } = $props();
</script>

<svg
	viewBox="0 0 96 197"
	fill="none"
	xmlns="http://www.w3.org/2000/svg"
	class={className}
	role="img"
	aria-label="Silitonix"
>
	<g>
		<path
			d="M70.9998 105.141L36.4999 70.9338L7.9182 42.5944C4.13058 38.8389 2 33.726 2 28.3922V4.7995L88.0818 90.1511C91.8694 93.9066 94 99.0195 94 104.353V137.068M2 54.5678V60.3191C2 65.653 4.13056 70.7658 7.91815 74.5213L70.9998 137.068M2 86.4947V92.246C2 97.5798 4.13059 102.693 7.91822 106.448L70.9998 168.995M70.9998 168.995L94 191.799V168.995H70.9998ZM2 123.385V168.995L25 191.799H70.9998L47.9999 168.995M47.9999 168.995H25V146.19L47.9999 168.995ZM38.7999 18.4825L25 4.7995H75.5998L94 23.0434V59.5313"
			stroke-width="4"
			stroke-linecap="square"
			stroke="#242424"
		/>
		<path
			filter="url(#logo-glow)"
			d="M70.9998 18.4825L77.8325 25.2572C79.3476 26.7594 80.1998 28.8046 80.1998 30.9381V45.8483"
			stroke-width="4"
			stroke-linecap="square"
			stroke="#242424"
		/>
	</g>
	<defs>
		<filter id="logo-glow" filterUnits="userSpaceOnUse" x="40" y="-20" width="70" height="100">
			{#each [{ dx: -2, dy: 2, blur: 2.5, dur: '9s', sat: 71, light: 42 }, { dx: -5, dy: 5, blur: 5, dur: '13s', sat: 100, light: 71 }] as shadow}
				<feDropShadow
					dx={shadow.dx}
					dy={shadow.dy}
					stdDeviation={shadow.blur}
					flood-color="hsl(0, 71%, 42%)"
				>
					<animate
						attributeName="flood-color"
						dur={shadow.dur}
						repeatCount="indefinite"
						values={`hsl(0,${shadow.sat}%,${shadow.light}%);hsl(60,${shadow.sat}%,${shadow.light}%);hsl(120,${shadow.sat}%,${shadow.light}%);hsl(180,${shadow.sat}%,${shadow.light}%);hsl(240,${shadow.sat}%,${shadow.light}%);hsl(300,${shadow.sat}%,${shadow.light}%);hsl(360,${shadow.sat}%,${shadow.light}%)`}
					/>
				</feDropShadow>
			{/each}
		</filter>
	</defs>
</svg>
