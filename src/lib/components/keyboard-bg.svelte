<script lang="ts">
	import { onMount } from 'svelte';

	const COUNT = 50;

	type Cell = { hue: number; lit: boolean };
	let cells = $state<Cell[]>(Array.from({ length: COUNT }, () => ({ hue: 0, lit: false })));

	onMount(() => {
		if (window.matchMedia('(prefers-reduced-motion: reduce)').matches) return;

		const timers = new Set<ReturnType<typeof setTimeout>>();
		let next: ReturnType<typeof setTimeout>;

		const flash = () => {
			const cell = cells[Math.floor(Math.random() * COUNT)];
			cell.hue = Math.floor(Math.random() * 360);
			cell.lit = true;

			const fade = setTimeout(() => {
				cell.lit = false;
				timers.delete(fade);
			}, 120);
			timers.add(fade);

			next = setTimeout(flash, 220 + Math.random() * 500);		};

		next = setTimeout(flash, 300);

		return () => {
			clearTimeout(next);
			timers.forEach(clearTimeout);
		};
	});
</script>

<div
	class="pointer-events-none absolute inset-0 grid grid-cols-[repeat(10,36px)] content-start gap-[5px] p-6"
	aria-hidden="true"
>
	{#each cells as cell}
		<div
			class="size-[36px] rounded-[5px] border border-neutral-200/70"
			class:transition-[background-color]={!cell.lit}
			class:duration-1000={!cell.lit}
			class:ease-out={!cell.lit}
			style:background-color={cell.lit ? `hsl(${cell.hue} 82% 83%)` : 'transparent'}
		></div>
	{/each}
</div>
