<script lang="ts">
	import { Button } from '$lib/components/ui/button/index.js';
	import { Separator } from '$lib/components/ui/separator/index.js';

	const updated = '20 November 2026';
</script>

<svelte:head>
	<title>Privacy Policy | Silitonix</title>
	<meta
		name="description"
		content="How silitonix.ir handles data, cookies and advertising, and the choices you have."
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
			A cookie is a small text file a website can store in your browser. This site does not set
			cookies of its own. Cookies may be set by the advertising service described below, which is
			operated by Google and its partners.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">Advertising</h2>
		<p class="text-neutral-600">
			We show ads through Google AdSense to keep the site free. Google, as a third-party vendor,
			uses cookies to serve ads on this site, including the DoubleClick cookie, which lets it and
			its partners serve ads based on your visits to this and other websites.
		</p>
		<p class="text-neutral-600">
			If you are in a region that requires it, you will be asked for consent before personalised
			ads are shown, and you can change or withdraw that choice at any time.
		</p>
		<p class="text-neutral-600">You can control or opt out of personalised advertising here:</p>
		<ul class="list-disc pl-5 text-neutral-600">
			<li>
				<a class="underline" href="https://adssettings.google.com" rel="noopener noreferrer">
					Google Ads Settings
				</a>
				— opt out of personalised Google ads
			</li>
			<li>
				<a class="underline" href="https://www.aboutads.info/choices/" rel="noopener noreferrer">
					aboutads.info
				</a>
				and
				<a class="underline" href="https://www.youronlinechoices.eu" rel="noopener noreferrer">
					Your Online Choices
				</a>
				— opt out from participating vendors
			</li>
			<li>
				<a
					class="underline"
					href="https://policies.google.com/technologies/partner-sites"
					rel="noopener noreferrer"
				>
					How Google uses information from sites that use its services
				</a>
			</li>
		</ul>
		<p class="text-neutral-600">
			Opting out does not remove ads; it makes them less relevant to you. Ad blockers also
			prevent these cookies from being set.
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
			For data held by Google as an advertising provider, use the links above or contact Google
			directly.
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
