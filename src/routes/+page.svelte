<script lang="ts">
	import ShaderBackground from '$lib/components/shader-background.svelte';
	import { Button } from '$lib/components/ui/button/index.js';
</script>

<svelte:head>
	<title>Silitonix</title>
	<meta name="description" content="Silitonix" />
</svelte:head>

<div class="relative h-svh overflow-hidden bg-white">
	<ShaderBackground />

	<header
		dir="ltr"
		class="absolute inset-x-0 top-0 z-10 flex h-14 items-center justify-between px-6"
	>
		<span class="text-sm font-semibold tracking-widest">SILITONIX</span>
		<nav class="flex items-center gap-1">
			<Button variant="ghost" size="sm">Products</Button>
			<Button variant="ghost" size="sm">About</Button>
			<Button variant="ghost" size="sm">Contact</Button>
		</nav>
	</header>

	<main dir="ltr" class="relative grid h-full place-items-center">
		<h1 class="pl-[0.3em] text-5xl font-bold tracking-[0.3em] sm:text-7xl">SILITONIX</h1>
	</main>
</div>
