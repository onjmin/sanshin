<script lang="ts">
	export let data;
</script>

<div class="min-h-dvh flex flex-col bg-gray-50 text-gray-900">
	<header
		class="border-b bg-white/80 backdrop-blur supports-[backdrop-filter]:bg-white/60"
	>
		<div
			class="max-w-5xl mx-auto px-4 py-4 flex items-center justify-between gap-4"
		>
			<a
				href="/"
				class="inline-flex items-center gap-2 font-semibold text-lg tracking-tight"
			>
				<span
					class="inline-grid place-items-center w-8 h-8 rounded-xl bg-emerald-600 text-white font-bold"
					>SS</span
				>
				<span>三蔵新山株式会社</span>
			</a>
			<nav class="flex items-center gap-5 text-sm">
				<a href="/" class="hover:underline underline-offset-4"
					>会社概要</a
				>
				<a href="/news" class="hover:underline underline-offset-4"
					>ニュース</a
				>
				<a href="/contact" class="hover:underline underline-offset-4"
					>お問い合わせ</a
				>
			</nav>
		</div>
	</header>

	<main class="flex-1">
		<slot />
	</main>

	<footer class="border-t bg-white">
		<div
			class="max-w-5xl mx-auto px-4 py-6 text-sm text-gray-600 flex flex-wrap items-center justify-between gap-3"
		>
			<p>
				© {new Date().getFullYear()} 三蔵新山株式会社（Sanzō‑Shinzan Co.,
				Ltd.）
			</p>
			<p class="italic">スローガン：『都市と自然を、やさしくむすぶ』</p>
		</div>
	</footer>
</div>

<style>
	/* 画面幅が極端に広いときの可読性確保 */
	:global(body) {
		@apply antialiased;
	}
</style>
