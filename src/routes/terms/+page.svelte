<script lang="ts">
	import { Button } from '$lib/components/ui/button/index.js';
	import { Separator } from '$lib/components/ui/separator/index.js';
</script>

<svelte:head>
	<title>شرایط استفاده | Silitonix</title>
	<meta name="description" content="شرایط استفاده از سایت Silitonix." />
</svelte:head>

<div class="mx-auto flex min-h-screen max-w-3xl flex-col gap-6 p-6">
	<header class="flex items-center justify-between gap-4">
		<h1 class="text-2xl font-bold">شرایط استفاده</h1>
		<Button variant="ghost" size="sm" href="/">بازگشت</Button>
	</header>
	<Separator />

	<p class="text-muted-foreground">آخرین به‌روزرسانی: نوامبر ۲۰۲۶</p>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">پذیرش شرایط</h2>
		<p class="text-muted-foreground">
			با استفاده از این سایت می‌پذیرید که این یک صفحهٔ نمایشی است و محتوای آن
			تضمینی برای هیچ خدمتی نیست.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">استفادهٔ مجاز</h2>
		<p class="text-muted-foreground">
			از این سایت برای فعالیت غیرقانونی، آسیب به سرویس یا نقض حقوق دیگران
			استفاده نکنید.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">محدودیت مسئولیت</h2>
		<p class="text-muted-foreground">
			این سایت «همان‌طور که هست» ارائه می‌شود و هیچ ضمانت صریح یا ضمنی ندارد.
			مسئولیت استفاده از آن با شماست.
		</p>
	</section>

	<section class="flex flex-col gap-2">
		<h2 class="text-xl font-semibold">تغییرات</h2>
		<p class="text-muted-foreground">
			این شرایط ممکن است بدون اطلاع قبلی تغییر کند. نسخهٔ جاری همیشه در همین
			صفحه در دسترس است.
		</p>
	</section>

	<footer class="mt-auto text-sm text-muted-foreground">
		<Button variant="link" size="sm" href="/privacy">حریم خصوصی</Button>
	</footer>
</div>
