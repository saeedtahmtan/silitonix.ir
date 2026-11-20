<script lang="ts">
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { Button } from '$lib/components/ui/button/index.js';
	import * as Card from '$lib/components/ui/card/index.js';
	import { Input } from '$lib/components/ui/input/index.js';
	import { Label } from '$lib/components/ui/label/index.js';
	import * as Alert from '$lib/components/ui/alert/index.js';
	import { Separator } from '$lib/components/ui/separator/index.js';
	import * as Tabs from '$lib/components/ui/tabs/index.js';

	let email = $state('');
	let sent = $state(false);
</script>

<svelte:head>
	<title>Silitonix — نمونهٔ رابط کاربری</title>
	<meta
		name="description"
		content="نمونهٔ صفحهٔ نمایشی Silitonix ساخته‌شده با Svelte و shadcn-svelte."
	/>
</svelte:head>

<div class="mx-auto flex min-h-screen max-w-3xl flex-col gap-8 p-6">
	<header class="flex flex-wrap items-center justify-between gap-4">
		<div class="flex items-center gap-2">
			<h1 class="text-2xl font-bold">سیلیتونیکس</h1>
			<Badge variant="secondary">نمایشی</Badge>
		</div>
		<nav class="flex items-center gap-2">
			<Button variant="ghost" size="sm" href="/privacy">حریم خصوصی</Button>
			<Button variant="ghost" size="sm" href="/terms">شرایط استفاده</Button>
		</nav>
	</header>

	<Separator />

	<section class="flex flex-col gap-3">
		<h2 class="text-3xl font-bold">یک صفحهٔ نمایشی با shadcn-svelte</h2>
		<p class="text-muted-foreground">
			این سایت یک نمونهٔ سبک است که فقط از اجزای shadcn-svelte استفاده می‌کند:
			کارت، نشان، هشدار، زبانه، ورودی و دکمه. هیچ سروری در کار نیست و همهٔ
			صفحه‌ها به‌صورت ایستا منتشر می‌شوند.
		</p>
		<div class="flex flex-wrap gap-2">
			<Button href="/terms">شروع کنید</Button>
			<Button variant="outline" href="/privacy">حریم خصوصی</Button>
		</div>
	</section>

	<div class="grid gap-4 sm:grid-cols-2">
		<Card.Root>
			<Card.Header>
				<Card.Title>سبک و سریع</Card.Title>
				<Card.Description>ساخته‌شده با Svelte 5 و Tailwind CSS.</Card.Description>
			</Card.Header>
			<Card.Content>
				<p class="text-sm text-muted-foreground">
					خروجی نهایی فقط فایل‌های ایستا است و می‌توان آن را روی هر میزبان
					ساده‌ای منتشر کرد.
				</p>
			</Card.Content>
		</Card.Root>

		<Card.Root>
			<Card.Header>
				<Card.Title>دسترس‌پذیر</Card.Title>
				<Card.Description>اجزای shadcn-svelte روی bits-ui ساخته شده‌اند.</Card.Description>
			</Card.Header>
			<Card.Content>
				<p class="text-sm text-muted-foreground">
					پیمایش با صفحه‌کلید و برچسب‌های مناسب از همان ابتدا در دسترس است.
				</p>
			</Card.Content>
		</Card.Root>
	</div>

	<Alert.Root>
		<Alert.Title>این یک صفحهٔ نمایشی است</Alert.Title>
		<Alert.Description>
			محتوای این سایت برای آزمون اجزای رابط کاربری است و خدماتی ارائه نمی‌دهد.
		</Alert.Description>
	</Alert.Root>

	<Tabs.Root value="about">
		<Tabs.List>
			<Tabs.Trigger value="about">درباره</Tabs.Trigger>
			<Tabs.Trigger value="stack">فناوری‌ها</Tabs.Trigger>
		</Tabs.List>
		<Tabs.Content value="about">
			<Card.Root class="mt-2">
				<Card.Header>
					<Card.Title>سیلیتونیکس</Card.Title>
					<Card.Description>نمونهٔ رابط کاربری فارسی و راست‌به‌چپ.</Card.Description>
				</Card.Header>
			</Card.Root>
		</Tabs.Content>
		<Tabs.Content value="stack">
			<Card.Root class="mt-2">
				<Card.Content class="flex flex-wrap gap-2 pt-6">
					<Badge>Svelte 5</Badge>
					<Badge variant="secondary">SvelteKit</Badge>
					<Badge variant="outline">Tailwind CSS</Badge>
					<Badge variant="outline">shadcn-svelte</Badge>
				</Card.Content>
			</Card.Root>
		</Tabs.Content>
	</Tabs.Root>

	<Card.Root>
		<Card.Header>
			<Card.Title>خبرنامه</Card.Title>
			<Card.Description>فقط برای نمایش فرم؛ چیزی ارسال نمی‌شود.</Card.Description>
		</Card.Header>
		<Card.Content>
			<form
				class="flex flex-col gap-3"
				onsubmit={(event) => {
					event.preventDefault();
					sent = true;
				}}
			>
				<div class="grid gap-2">
					<Label for="email">ایمیل</Label>
					<Input id="email" type="email" bind:value={email} placeholder="you@example.com" required />
				</div>
				<Button type="submit">ثبت</Button>
				{#if sent}
					<p class="text-sm text-muted-foreground">ثبت شد (نمایشی).</p>
				{/if}
			</form>
		</Card.Content>
	</Card.Root>

	<footer class="mt-auto flex flex-wrap items-center justify-between gap-2 text-sm text-muted-foreground">
		<span>© ۲۰۲۶ Silitonix</span>
		<div class="flex gap-2">
			<Button variant="link" size="sm" href="/privacy">حریم خصوصی</Button>
			<Button variant="link" size="sm" href="/terms">شرایط استفاده</Button>
		</div>
	</footer>
</div>
