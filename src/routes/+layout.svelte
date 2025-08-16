<!-- src/routes/+layout.svelte -->
<script lang="ts">
	import "../app.css";
	import { resolve } from "$app/paths";

	export let data;
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

			<!-- ナビゲーション -->
			<nav class="flex items-center gap-6 text-sm font-medium">
				<a
					href="timetable"
					class="text-gray-700 hover:text-emerald-700 transition-colors"
					>時刻表</a
				>
				<a
					href="ekiben"
					class="text-gray-700 hover:text-emerald-700 transition-colors"
					>駅弁</a
				>
				<a
					href="news"
					class="text-gray-700 hover:text-emerald-700 transition-colors"
					>ニュース</a
				>
				<a
					href="recruit"
					class="text-gray-700 hover:text-emerald-700 transition-colors"
					>採用</a
				>
			</nav>
		</div>

		<!-- 下ライン（鉄道のレールをイメージ） -->
		<div
			class="h-1 bg-gradient-to-r from-emerald-600 via-cyan-500 to-emerald-600"
		></div>
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
