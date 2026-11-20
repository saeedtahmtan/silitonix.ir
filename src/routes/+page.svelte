<script lang="ts">
	import KeyboardBg from '$lib/components/keyboard-bg.svelte';
	import Logo from '$lib/components/logo.svelte';
	import ShaderBackground from '$lib/components/shader-background.svelte';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { Button, buttonVariants } from '$lib/components/ui/button/index.js';
	import * as Card from '$lib/components/ui/card/index.js';
	import * as DropdownMenu from '$lib/components/ui/dropdown-menu/index.js';
	import { ScrollArea } from '$lib/components/ui/scroll-area/index.js';

	const email = 'silitonix@gmail.com';
</script>

<svelte:head>
	<title>Silitonix — products for the web</title>
	<meta
		name="description"
		content="Silitonix makes small, focused web products. Our first product is Dingotype, a minimal typing test with word translations."
	/>
</svelte:head>

<div class="relative h-svh overflow-hidden bg-white">
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

	<ScrollArea class="h-svh">
	<section
		dir="ltr"
		class="relative flex h-svh cursor-crosshair flex-col items-center justify-center overflow-hidden px-6 text-center"
	>
		<ShaderBackground />

		<div class="relative z-10">
			<div class="mx-auto w-fit" data-shader-avoid>
				<Logo class="h-40 w-auto text-neutral-900 sm:h-52" />
			</div>
			<p class="mt-6 text-2xl font-bold tracking-[0.25em] text-neutral-900">The silitonix</p>
			<p class="mt-3 text-sm text-neutral-700">
				Small, focused products for the web. Built to be fast, private and simple.
			</p>
		</div>
	</section>

	<section
		id="products"
		dir="ltr"
		class="relative flex min-h-svh flex-col items-center justify-center gap-6 px-6 py-20"
	>
		<h2 class="text-2xl font-semibold">Products</h2>

		<Card.Root
			class="relative w-full max-w-[453px] overflow-hidden border-neutral-200 bg-white/85 text-left backdrop-blur-sm"
		>
			<KeyboardBg />
			<Card.Header class="relative">
				<Card.Title class="flex items-center gap-2">
					Dingotype
					<Badge variant="secondary">Product</Badge>
				</Card.Title>
				<Card.Description>
					A minimal typing test with word translations. Track your speed, practise words you
					miss and improve — no account, no server, everything stays in your browser.
				</Card.Description>
			</Card.Header>
			<Card.Content class="relative text-sm text-neutral-600">
				Open source, free to use, and available in Persian and English.
			</Card.Content>
			<Card.Footer class="relative -mt-3">
				<Button class="h-[36px] w-[200px]" href="https://dingotype.silitonix.ir/" rel="noopener">
					Visit Dingotype
				</Button>
			</Card.Footer>
		</Card.Root>
	</section>

	<footer
		dir="ltr"
		class="relative flex h-16 items-center justify-between border-t border-neutral-200/70 bg-white/70 px-6 text-xs text-neutral-500 backdrop-blur-sm"
	>
		<span>© 2026 Silitonix</span>
		<nav class="flex items-center gap-4">
			<a class="hover:text-neutral-900" href="/privacy">Privacy</a>
			<a class="hover:text-neutral-900" href="/terms">Terms</a>
			<a class="hover:text-neutral-900" href={`mailto:${email}`}>{email}</a>
		</nav>
	</footer>
	</ScrollArea>
</div>
