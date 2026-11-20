<script lang="ts">
	import { Button } from '$lib/components/ui/button/index.js';
	import { Separator } from '$lib/components/ui/separator/index.js';

	const updated = '20 November 2026';
</script>

<svelte:head>
	<title>Terms of Service | Silitonix</title>
	<meta
		name="description"
		content="The terms that apply when you use silitonix.ir, including use of the site, our products and liability."
	/>
</svelte:head>

<div class="mx-auto flex min-h-screen max-w-2xl flex-col gap-6 p-6">
	<header class="flex items-center justify-between gap-4">
		<h1 class="text-2xl font-bold">Terms of Service</h1>
		<Button variant="ghost" size="sm" href="/">Back</Button>
	</header>
	<Separator />

	<p class="text-sm text-neutral-500">Last updated: {updated}</p>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">1. Acceptance</h2>
		<p class="text-neutral-600">
			These terms apply to silitonix.ir, operated by Silitonix. By visiting the site you agree to
			them. If you do not agree, please stop using the site.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">2. Use of the site</h2>
		<p class="text-neutral-600">You may read the site and follow links to our products. You agree not to:</p>
		<ul class="list-disc pl-5 text-neutral-600">
			<li>use the site in a way that breaks the law;</li>
			<li>attempt to gain unauthorised access to the site, its host or other visitors;</li>
			<li>send automated traffic that degrades the site for others, such as scraping at scale or
				load testing without permission;</li>
			<li>copy the site in a way that misrepresents it as your own.</li>
		</ul>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">3. Content and intellectual property</h2>
		<p class="text-neutral-600">
			The name Silitonix, the logo and the text and design of this site belong to us. You may share
			links to the site and quote short passages with attribution. Do not use our branding in a way
			that suggests we endorse you or your product without asking us first.
		</p>
		<p class="text-neutral-600">
			Any open-source code released by us is licensed under the terms included with that project,
			not by these terms.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">4. Our products</h2>
		<p class="text-neutral-600">
			Products linked from this site, such as Dingotype, are separate applications with their own
			features, storage and rules. Links are provided for convenience. Using a product means
			agreeing to the terms shown on its own site.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">5. Advertising</h2>
		<p class="text-neutral-600">
			Parts of the site may show ads provided by third parties such as Google. We do not control
			ad content and are not responsible for the products or sites advertised. See our
			<a class="underline" href="/privacy">Privacy Policy</a> for how advertising cookies
			work and how to opt out.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">6. No warranty</h2>
		<p class="text-neutral-600">
			The site is provided “as is” and “as available”, without warranties of any kind, whether
			express or implied. We do not promise that the site will be available without interruption,
			free of errors, or that any information on it is complete or current.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">7. Limitation of liability</h2>
		<p class="text-neutral-600">
			To the fullest extent permitted by law, we are not liable for any indirect, incidental or
			consequential loss, or for any loss of data, income or profit, arising from your use of or
			inability to use the site or any site we link to. Nothing in these terms limits rights you
			have under mandatory consumer law.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">8. Links to other sites</h2>
		<p class="text-neutral-600">
			We are not responsible for the content, policies or practices of websites we do not operate,
			including those we link to and those that advertise here.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">9. Changes</h2>
		<p class="text-neutral-600">
			We may update these terms as the site changes. The date above shows the current version, and
			continuing to use the site after a change means you accept the new terms.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">10. If part of these terms is unenforceable</h2>
		<p class="text-neutral-600">
			If any provision is found to be invalid, the rest stays in force and the invalid provision is
			read in the way that comes closest to its intent.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">11. Contact</h2>
		<p class="text-neutral-600">
			Questions about these terms? Email
			<a class="underline" href="mailto:silitonix@gmail.com">silitonix@gmail.com</a>.
		</p>
	</section>

	<footer class="mt-auto flex items-center gap-3 text-sm text-neutral-500">
		<a class="underline" href="/privacy">Privacy Policy</a>
		<span>·</span>
		<a class="underline" href="/">Home</a>
	</footer>
</div>
