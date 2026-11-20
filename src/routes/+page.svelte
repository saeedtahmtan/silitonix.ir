<script lang="ts">
	import ShaderBackground from '$lib/components/shader-background.svelte';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { Button } from '$lib/components/ui/button/index.js';
	import * as Card from '$lib/components/ui/card/index.js';
</script>

<svelte:head>
	<title>Silitonix — products for the web</title>
	<meta
		name="description"
		content="Silitonix makes small, focused web products. Our first product is Dingotype, a minimal typing test with word translations."
	/>
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

	<main
		dir="ltr"
		class="relative flex h-full flex-col items-center justify-center gap-7 px-6 text-center"
	>
		<div>
			<h1 class="pl-[0.3em] text-5xl font-bold tracking-[0.3em] sm:text-7xl">SILITONIX</h1>
			<p class="mt-4 text-sm text-neutral-600">
				Small, focused products for the web. Built to be fast, private and simple.
			</p>
		</div>

		<Card.Root class="w-full max-w-md border-neutral-200 bg-white/85 text-left backdrop-blur-sm">
			<Card.Header>
				<Card.Title class="flex items-center gap-2">
					Dingotype
					<Badge variant="secondary">Product</Badge>
				</Card.Title>
				<Card.Description>
					A minimal typing test with word translations. Track your speed, practise words you
					miss and improve — no account, no server, everything stays in your browser.
				</Card.Description>
			</Card.Header>
			<Card.Content class="text-sm text-neutral-600">
				Open source, free to use, and available in Persian and English.
			</Card.Content>
			<Card.Footer>
				<Button href="https://dingotype.silitonix.ir/" rel="noopener">
					Visit Dingotype
				</Button>
			</Card.Footer>
		</Card.Root>
	</main>

	<footer
		dir="ltr"
		class="absolute inset-x-0 bottom-0 z-10 flex h-12 items-center justify-between px-6 text-xs text-neutral-500"
	>
		<span>© 2026 Silitonix</span>
		<nav class="flex items-center gap-4">
			<a class="hover:text-neutral-900" href="/privacy.html">Privacy</a>
			<a class="hover:text-neutral-900" href="/terms.html">Terms</a>
		</nav>
	</footer>
</div>
