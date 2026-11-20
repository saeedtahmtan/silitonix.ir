<script lang="ts">
	import ShaderBackground from '$lib/components/shader-background.svelte';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { Button, buttonVariants } from '$lib/components/ui/button/index.js';
	import * as Card from '$lib/components/ui/card/index.js';
	import * as DropdownMenu from '$lib/components/ui/dropdown-menu/index.js';

	const email = 'silitonix@gmail.com';
</script>

<svelte:head>
	<title>Silitonix — products for the web</title>
	<meta
		name="description"
		content="Silitonix makes small, focused web products. Our first product is Dingotype, a minimal typing test with word translations."
	/>
</svelte:head>

<div class="relative min-h-svh bg-white">
	<header
		dir="ltr"
		class="fixed inset-x-0 top-0 z-20 flex h-14 items-center justify-between bg-white/60 px-6 backdrop-blur-sm"
	>
		<span class="text-sm font-semibold tracking-widest">SILITONIX</span>
		<nav class="flex items-center gap-1">
			<a class={buttonVariants({ variant: 'ghost', size: 'sm' })} href="#products">Products</a>
			<Button variant="ghost" size="sm">About</Button>
			<DropdownMenu.Root>
				<DropdownMenu.Trigger class={buttonVariants({ variant: 'ghost', size: 'sm' })}>
					Contact
				</DropdownMenu.Trigger>
				<DropdownMenu.Content align="end" class="w-64">
					<DropdownMenu.Label>Contact us</DropdownMenu.Label>
					<DropdownMenu.Separator />
					<DropdownMenu.Item onSelect={() => (window.location.href = `mailto:${email}`)}>
						{email}
					</DropdownMenu.Item>
				</DropdownMenu.Content>
			</DropdownMenu.Root>
		</nav>
	</header>

	<section
		dir="ltr"
		class="relative flex h-svh flex-col items-center justify-center overflow-hidden px-6 text-center"
	>
		<ShaderBackground />

		<h1 class="pl-[0.3em] text-5xl font-bold tracking-[0.3em] sm:text-7xl">SILITONIX</h1>
		<p class="mt-4 text-sm text-neutral-700">
			Small, focused products for the web. Built to be fast, private and simple.
		</p>
	</section>

	<section
		id="products"
		dir="ltr"
		class="relative flex min-h-svh flex-col items-center justify-center gap-6 px-6 py-20"
	>
		<h2 class="text-2xl font-semibold">Products</h2>

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
				<Button href="https://dingotype.silitonix.ir/" rel="noopener">Visit Dingotype</Button>
			</Card.Footer>
		</Card.Root>
	</section>

	<footer
		dir="ltr"
		class="relative flex h-16 items-center justify-between border-t border-neutral-200/70 bg-white/70 px-6 text-xs text-neutral-500 backdrop-blur-sm"
	>
		<span>© 2026 Silitonix</span>
		<nav class="flex items-center gap-4">
			<a class="hover:text-neutral-900" href="/privacy.html">Privacy</a>
			<a class="hover:text-neutral-900" href="/terms.html">Terms</a>
			<a class="hover:text-neutral-900" href={`mailto:${email}`}>{email}</a>
		</nav>
	</footer>
</div>
