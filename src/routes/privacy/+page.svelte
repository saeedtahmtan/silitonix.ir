<script lang="ts">
	import { Button } from '$lib/components/ui/button/index.js';
	import { Separator } from '$lib/components/ui/separator/index.js';

	const updated = '20 November 2026';
</script>

<svelte:head>
	<title>Privacy Policy | Silitonix</title>
	<meta
		name="description"
		content="What silitonix.ir does and does not collect, and how to reach us."
	/>
</svelte:head>

<div class="mx-auto flex min-h-screen max-w-2xl flex-col gap-6 p-6">
	<header class="flex items-center justify-between gap-4">
		<h1 class="text-2xl font-bold">Privacy Policy</h1>
		<Button variant="ghost" size="sm" href="/">Back</Button>
	</header>
	<Separator />

	<p class="text-sm text-neutral-500">Last updated: {updated}</p>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">Who we are</h2>
		<p class="text-neutral-600">
			silitonix.ir is a small website that introduces the products we build. You can reach us at
			<a class="underline" href="mailto:silitonix@gmail.com">silitonix@gmail.com</a> for anything in
			this policy.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">What we collect</h2>
		<p class="text-neutral-600">
			The site has no accounts and no backend of its own. We do not ask for your name, email or
			payment details, and we do not run our own analytics or tracking.
		</p>
		<p class="text-neutral-600">
			Anything you type into a demo on this site stays in your browser and is never sent to us.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">Cookies</h2>
		<p class="text-neutral-600">
			This site sets no cookies and loads no advertising or analytics scripts. Your visit is not
			tracked between pages or across sites.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">Hosting and server logs</h2>
		<p class="text-neutral-600">
			The site is served as static files by GitHub Pages. Like any host, GitHub may keep technical
			request logs such as your IP address, browser type and the time of your request, for
			security and reliability. We do not receive or store those logs ourselves.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">Links to other sites</h2>
		<p class="text-neutral-600">
			Our products, such as Dingotype, run on their own pages and may store data in your browser
			to keep your settings and results. Those sites are not covered by this policy; this policy
			applies to silitonix.ir only.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">Your rights</h2>
		<p class="text-neutral-600">
			Depending on where you live, you may have the right to ask what personal data is held about
			you, to have it corrected or deleted, or to object to certain processing. We hold no
			personal data about visitors, so in practice there is nothing for us to export or erase.
		</p>
		<p class="text-neutral-600">
			If you believe your data has been handled incorrectly, you can complain to your local data
			protection authority. You are also welcome to write to us first at
			<a class="underline" href="mailto:silitonix@gmail.com">silitonix@gmail.com</a>.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">Children</h2>
		<p class="text-neutral-600">
			The site is not directed at children under 13, and we do not knowingly collect information
			from them. If you believe a child has provided information to us, contact us and we will
			remove it.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">Changes to this policy</h2>
		<p class="text-neutral-600">
			We may update this policy as the site changes. The date at the top always shows the current
			version, and the latest text is always on this page.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">Contact</h2>
		<p class="text-neutral-600">
			Questions about privacy? Email
			<a class="underline" href="mailto:silitonix@gmail.com">silitonix@gmail.com</a>.
		</p>
	</section>

	<footer class="mt-auto flex items-center gap-3 text-sm text-neutral-500">
		<a class="underline" href="/terms">Terms of Service</a>
		<span>·</span>
		<a class="underline" href="/">Home</a>
	</footer>
</div>
