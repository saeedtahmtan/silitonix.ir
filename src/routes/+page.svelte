<script lang="ts">
	import { Button } from '$lib/components/ui/button/index.js';
</script>

<svelte:head>
	<title>Silitonix</title>
	<meta name="description" content="Silitonix" />
</svelte:head>

<div class="flex h-svh flex-col overflow-hidden">
	<header dir="ltr" class="flex h-14 shrink-0 items-center justify-between px-6">
		<span class="text-sm font-semibold tracking-widest">SILITONIX</span>
		<nav class="flex items-center gap-1">
			<Button variant="ghost" size="sm">Products</Button>
			<Button variant="ghost" size="sm">About</Button>
			<Button variant="ghost" size="sm">Contact</Button>
		</nav>
	</header>

	<main class="grid flex-1 place-items-center">
		<h1 class="text-5xl font-bold tracking-[0.3em] sm:text-7xl">SILITONIX</h1>
	</main>
</div>
