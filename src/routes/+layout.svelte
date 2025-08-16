<script lang="ts">
	import "../app.css";
	import { resolve } from "$app/paths";
	import { page } from "$app/state";
	import { derived } from "svelte/store";

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
		{ href: "/company", label: "会社概要" },
		{ href: "/recruit", label: "採用情報" },
		{ href: "/timetable", label: "時刻表" },
		{ href: "/ekiben", label: "駅弁" },
		{ href: "/news", label: "ニュース" },
	];
</script>

<div class="min-h-dvh flex flex-col bg-gray-50 text-gray-900 antialiased">
	<!-- ヘッダー -->
	<header class="bg-white/90 backdrop-blur border-b border-emerald-600/40">
		<div
			class="max-w-6xl mx-auto px-4 py-4 flex items-center justify-between gap-4"
		>
			<!-- ロゴ -->
			<a href={resolve("/")} class="flex items-center gap-3">
				<img
					src="https://i.imgur.com/AQV3TtI.png"
					alt="三蔵新山株式会社"
					class="w-10 h-10 rounded-lg shadow"
				/>
				<span
					class="font-semibold text-xl tracking-tight text-emerald-800"
				>
					三蔵新山株式会社
				</span>
			</a>

			<!-- ヘッダー右側のナビ -->
			<nav class="flex items-center gap-6 text-sm font-medium">
				<a
					href="company"
					class="text-gray-700 hover:text-emerald-700 transition-colors"
					>会社概要</a
				>
			</nav>
		</div>

		<!-- 下ライン（鉄道のレールをイメージ） -->
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
			page.url.pathname.startsWith(p.href)
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
			class="max-w-6xl mx-auto px-4 py-4 text-xs text-gray-500 text-center"
		>
			This site is a joke website created based on the 2ch thread "Let's
			make a cheap new train and troll train spotters lol".
		</div>
	</footer>
</div>
