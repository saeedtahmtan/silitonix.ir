<script lang="ts">
	import { Button } from '$lib/components/ui/button/index.js';
	import { Separator } from '$lib/components/ui/separator/index.js';
</script>

<svelte:head>
	<title>حریم خصوصی | Silitonix</title>
	<meta name="description" content="سیاست حریم خصوصی سایت Silitonix." />
</svelte:head>

<div class="mx-auto flex min-h-screen max-w-3xl flex-col gap-6 p-6">
	<header class="flex items-center justify-between gap-4">
		<h1 class="text-2xl font-bold">حریم خصوصی</h1>
		<Button variant="ghost" size="sm" href="/">بازگشت</Button>
	</header>
	<Separator />

	<p class="text-muted-foreground">آخرین به‌روزرسانی: نوامبر ۲۰۲۶</p>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">داده‌هایی که جمع می‌کنیم</h2>
		<p class="text-muted-foreground">
			این سایت سروری برای ثبت اطلاعات ندارد و حساب کاربری نمی‌سازد. فرم‌های
			نمایشی هیچ داده‌ای ارسال نمی‌کنند.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">کوکی‌ها و تبلیغات</h2>
		<p class="text-muted-foreground">
			این سایت از Google AdSense استفاده می‌کند. Google و شرکای آن ممکن است از
			کوکی‌ها برای نمایش تبلیغات بر اساس بازدیدهای قبلی شما از این سایت یا
			سایت‌های دیگر استفاده کنند. می‌توانید تبلیغات شخصی‌سازی‌شده را از طریق
			<a class="underline" href="https://adssettings.google.com" rel="noopener noreferrer">
				تنظیمات تبلیغات Google
			</a>
			غیرفعال کنید. برای جزئیات بیشتر
			<a class="underline" href="https://policies.google.com/technologies/partner-sites" rel="noopener noreferrer">
				سیاست حریم خصوصی شرکای Google
			</a>
			را ببینید.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">میزبانی</h2>
		<p class="text-muted-foreground">
			فایل‌های این سایت به‌صورت ایستا میزبانی می‌شوند. میزبان ممکن است مانند هر
			وب‌سروری نشانی IP و اطلاعات فنی درخواست‌ها را برای امنیت و آمار نگه دارد.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">تغییرات</h2>
		<p class="text-muted-foreground">
			این سیاست ممکن است به‌روزرسانی شود. نسخهٔ جاری همیشه در همین صفحه در
			دسترس است.
		</p>
	</section>

	<footer class="mt-auto text-sm text-muted-foreground">
		<Button variant="link" size="sm" href="/terms">شرایط استفاده</Button>
	</footer>
</div>
