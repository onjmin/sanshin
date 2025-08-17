<script lang="ts">
	import "../app.css";
	import { resolve } from "$app/paths";
	import { page } from "$app/state";

	const routes = [
		"/",
		"/company",
		"/recruit",
		"/timetable",
		"/ekiben",
		"/news",
	] as const;

	type Route = (typeof routes)[number];

	const pages: { href: Route; label: string }[] = [
		{ href: "/", label: "ホーム" },
		{ href: "/company", label: "会社概要" },
		{ href: "/recruit", label: "採用情報" },
		{ href: "/timetable", label: "時刻表" },
		{ href: "/ekiben", label: "駅弁" },
		{ href: "/news", label: "ニュース" },
	];

	const title = "三蔵新山株式会社";
	const description =
		"都市と自然を、やさしくむすぶ ― 三蔵新山株式会社 公式サイト";
	const image = "https://i.imgur.com/AQV3TtI.png";
</script>

<svelte:head>
	<title>{title}</title>
	<meta name="description" content={description} />

	<!-- Open Graph -->
	<meta property="og:title" content={title} />
	<meta property="og:description" content={description} />
	<meta property="og:type" content="website" />
	<meta property="og:url" content={resolve("/")} />
	<meta property="og:image" content={image} />

	<!-- Twitter Card -->
	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:title" content={title} />
	<meta name="twitter:description" content={description} />
	<meta name="twitter:image" content={image} />

	<!-- Apple Touch Icon -->
	<link rel="apple-touch-icon" href={image} />

	<meta name="theme-color" content="#047857" />

	<script
		src="https://cdn.jsdelivr.net/npm/gif.js.optimized/dist/gif.js"
	></script>
</svelte:head>

<div class="min-h-dvh flex flex-col bg-gray-50 text-gray-900 antialiased">
	<!-- ヘッダー -->
	<header class="bg-white/90 backdrop-blur border-b border-emerald-600/40">
		<div
			class="h-1 bg-gradient-to-r from-emerald-600 via-cyan-500 to-emerald-600"
		></div>

		<!-- パンくずっぽいナビゲーション -->
		<nav class="flex gap-4 px-4 py-2 bg-emerald-700 text-white text-sm">
			{#each pages as p}
				<a
					href={resolve(p.href)}
					class={`px-3 py-1 rounded-md transition-colors
        ${
			p.href !== "/" && page.url.pathname.includes(p.href)
				? "bg-emerald-500 font-semibold"
				: "hover:bg-emerald-600"
		}
      `}
				>
					{p.label}
				</a>
			{/each}
		</nav>
	</header>

	<!-- メイン -->
	<main class="flex-1">
		<slot />
	</main>

	<!-- フッター -->
	<footer class="border-t bg-white mt-12">
		<div
			class="max-w-6xl mx-auto px-4 py-4 text-xs text-red-600 text-center"
		>
			このサイトはおーぷん２ちゃんねるのスレ「安価で新しい電車作って撮り鉄釣ろうぜwwwww」で作られたジョークサイトです。
		</div>
	</footer>
</div>
