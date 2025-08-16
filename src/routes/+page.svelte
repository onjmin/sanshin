<script>
    import VoicePart from "$lib/components/VoicePart.svelte";
</script>

<section
    class="relative bg-gradient-to-b from-emerald-50 to-white min-h-screen"
>
    <!-- ヒーロー -->
    <div class="relative overflow-hidden bg-emerald-700 text-white">
        <!-- 背景画像 (半透明) -->
        <div
            class="absolute inset-0 bg-cover bg-center opacity-50"
            style="background-image: url('https://i.imgur.com/gnxdDLE.jpeg');"
        ></div>

        <!-- コンテンツ -->
        <div class="relative max-w-6xl mx-auto px-6 py-16 md:py-24 text-center">
            <h1 class="text-4xl md:text-5xl font-bold tracking-tight">
                三蔵新山株式会社
            </h1>
            <p class="mt-4 text-lg md:text-xl opacity-90">
                都市と自然を、やさしくむすぶ
            </p>

            <!-- メイン導線ボタン -->
            <div class="mt-8 flex flex-wrap justify-center gap-4">
                <a
                    href="company"
                    class="px-6 py-3 bg-white text-emerald-700 font-semibold rounded-full shadow hover:bg-gray-100"
                >
                    会社概要
                </a>
                <a
                    href="business"
                    class="px-6 py-3 bg-white text-emerald-700 font-semibold rounded-full shadow hover:bg-gray-100"
                >
                    事業紹介
                </a>
                <a
                    href="recruit"
                    class="px-6 py-3 bg-white text-emerald-700 font-semibold rounded-full shadow hover:bg-gray-100"
                >
                    採用情報
                </a>
                <a
                    href="https://hayabusa.open2ch.net/test/read.cgi/livejupiter/1755327173/l30"
                    class="px-6 py-3 bg-white text-emerald-700 font-semibold rounded-full shadow hover:bg-gray-100"
                >
                    お問い合わせ
                </a>
            </div>
        </div>

        <!-- 下部のグラデーション帯 -->
        <div
            class="absolute bottom-0 left-0 right-0 h-2 bg-gradient-to-r from-emerald-600 via-cyan-500 to-emerald-600"
        ></div>

        <!-- 注意書き -->
        <span class="absolute bottom-2 right-4 text-xs opacity-70 text-red-500">
            ※This web site is a fiction.
        </span>
    </div>

    <!-- ニュースリリース -->
    <div class="max-w-5xl mx-auto px-4 py-12">
        <h2
            class="text-2xl font-semibold text-emerald-800 mb-6 border-l-4 border-emerald-600 pl-3"
        >
            ニュースリリース
        </h2>
        <ul class="space-y-4">
            <li class="border-b pb-2">
                <span class="text-sm text-gray-500 mr-2">2025/08/10</span>
                <a
                    href="news/20250810"
                    class="text-emerald-700 font-medium hover:underline"
                >
                    新線「三山本線」延伸計画を発表
                </a>
            </li>
            <li class="border-b pb-2">
                <span class="text-sm text-gray-500 mr-2">2025/07/30</span>
                <a
                    href="news/20250730"
                    class="text-emerald-700 font-medium hover:underline"
                >
                    夏の観光キャンペーン開始
                </a>
            </li>
        </ul>
    </div>

    <!-- SNSリンク -->
    <div class="max-w-5xl mx-auto px-4 pb-16 text-center">
        <h2
            class="text-2xl font-semibold text-emerald-800 mb-6 border-l-4 border-emerald-600 pl-3 text-left"
        >
            公式アカウント
        </h2>
        <div class="flex justify-center gap-6 text-emerald-700 text-3xl">
            <a href="https://twitter.com/" target="_blank" aria-label="Twitter">
                <i class="fa-brands fa-twitter"></i>
            </a>
            <a
                href="https://facebook.com/"
                target="_blank"
                aria-label="Facebook"
            >
                <i class="fa-brands fa-facebook"></i>
            </a>
            <a
                href="https://instagram.com/"
                target="_blank"
                aria-label="Instagram"
            >
                <i class="fa-brands fa-instagram"></i>
            </a>
            <a href="https://youtube.com/" target="_blank" aria-label="YouTube">
                <i class="fa-brands fa-youtube"></i>
            </a>
        </div>
    </div>
    <VoicePart />
</section>

<svelte:head>
    <title>三蔵新山株式会社（SS鉄道） | 都市と自然を、やさしくむすぶ</title>
    <meta
        name="description"
        content="三蔵新山株式会社（SS鉄道）の公式サイト。沿線情報、運行情報、駅・車両の特徴、沿線の観光・地域情報などをご紹介します。"
    />
</svelte:head>
