<script lang="ts">
	import { Button } from '$lib/components/ui/button/index.js';
	import { Separator } from '$lib/components/ui/separator/index.js';
</script>

<svelte:head>
	<title>Terms of Service | Silitonix</title>
	<meta name="description" content="Terms of service for using silitonix.ir." />
</svelte:head>

<div class="mx-auto flex min-h-screen max-w-2xl flex-col gap-6 p-6">
	<header class="flex items-center justify-between gap-4">
		<h1 class="text-2xl font-bold">Terms of Service</h1>
		<Button variant="ghost" size="sm" href="/">Back</Button>
	</header>
	<Separator />

	<p class="text-sm text-neutral-500">Last updated: November 2026</p>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">Acceptance</h2>
		<p class="text-neutral-600">
			By using this site you agree to these terms. If you do not agree, do not use the site.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">Use of the site</h2>
		<p class="text-neutral-600">
			You may browse this site and follow links to our products. Do not use the site to break
			the law, attack or overload the service, or interfere with other visitors.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">Products</h2>
		<p class="text-neutral-600">
			Products linked from this site, such as Dingotype, are separate applications with their
			own behaviour and terms. Links are provided for convenience; we are not responsible for
			third-party websites we do not operate.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">No warranty</h2>
		<p class="text-neutral-600">
			The site is provided “as is” and “as available”, without warranties of any kind. To the
			extent permitted by law, we are not liable for any loss arising from use of the site.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">Changes</h2>
		<p class="text-neutral-600">
			We may change these terms at any time. Continuing to use the site means you accept the
			current version.
		</p>
	</section>

	<footer class="mt-auto text-sm text-neutral-500">
		<a class="underline" href="/privacy.html">Privacy Policy</a>
	</footer>
</div>
