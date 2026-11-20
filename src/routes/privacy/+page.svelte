<script lang="ts">
	import { Button } from '$lib/components/ui/button/index.js';
	import { Separator } from '$lib/components/ui/separator/index.js';
</script>

<svelte:head>
	<title>Privacy Policy | Silitonix</title>
	<meta
		name="description"
		content="How Silitonix handles data, cookies and advertising on silitonix.ir."
	/>
</svelte:head>

<div class="mx-auto flex min-h-screen max-w-2xl flex-col gap-6 p-6">
	<header class="flex items-center justify-between gap-4">
		<h1 class="text-2xl font-bold">Privacy Policy</h1>
		<Button variant="ghost" size="sm" href="/">Back</Button>
	</header>
	<Separator />

	<p class="text-sm text-neutral-500">Last updated: November 2026</p>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">Data we collect</h2>
		<p class="text-neutral-600">
			This site has no accounts and no backend. It does not collect, store or send personal
			information. Anything you type into a demo form stays in your browser and is not
			submitted anywhere.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">Cookies and advertising</h2>
		<p class="text-neutral-600">
			This site uses Google AdSense to show ads. Google and its partners may use cookies to
			serve ads based on your previous visits to this or other websites. You can opt out of
			personalised advertising in
			<a class="underline" href="https://adssettings.google.com" rel="noopener noreferrer">
				Google Ads Settings </a
			>. See also
			<a
				class="underline"
				href="https://policies.google.com/technologies/partner-sites"
				rel="noopener noreferrer"
			>
				how Google uses information from partner sites </a
			>.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">Hosting</h2>
		<p class="text-neutral-600">
			The site is served as static files from GitHub Pages. Like any web host, it may keep
			technical request logs (such as IP address and user agent) for security and
			reliability.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">External links</h2>
		<p class="text-neutral-600">
			Products linked from this site, such as Dingotype, run on their own pages and store
			data in your browser only. This policy covers silitonix.ir.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">Changes</h2>
		<p class="text-neutral-600">
			This policy may be updated. The current version is always available on this page.
		</p>
	</section>

	<footer class="mt-auto text-sm text-neutral-500">
		<a class="underline" href="/terms.html">Terms of Service</a>
	</footer>
</div>
