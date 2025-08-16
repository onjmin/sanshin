<script lang="ts">
    import VoicePart from "$lib/components/VoicePart.svelte";

    const profile: { label: string; value: string }[] = [
        { label: "社名", value: "三蔵新山株式会社（Sanzō-Shinzan Co., Ltd.）" },
        { label: "略称", value: "三新（さんしん）、SS鉄道" },
        { label: "本社所在地", value: "東京都文京区三山町1-45（架空住所）" },
        { label: "設立", value: "1957年（昭和32年）5月1日" },
        { label: "資本金", value: "150億円（非上場）" },
        { label: "代表取締役社長", value: "新山透（しんざん とおる）" },
        { label: "従業員数", value: "約3,400名（グループ全体）" },
        { label: "スローガン", value: "「都市と自然を、やさしくむすぶ」" },
    ];
</script>

<section
    class="relative bg-gradient-to-b from-emerald-50 to-white min-h-screen"
>
    <!-- ヒーローヘッダー -->
    <div class="relative overflow-hidden bg-emerald-700 text-white">
        <div class="max-w-6xl mx-auto px-6 py-16 md:py-24 text-center">
            <h1 class="text-4xl md:text-5xl font-bold tracking-tight">
                三蔵新山株式会社
            </h1>
            <p class="mt-4 text-lg md:text-xl opacity-90">
                都市と自然を、やさしくむすぶ
            </p>
        </div>

        <!-- 路線をイメージした装飾ライン -->
        <div
            class="absolute bottom-0 left-0 right-0 h-2 bg-gradient-to-r from-emerald-600 via-cyan-500 to-emerald-600"
        ></div>

        <!-- 右下端にフィクション文言 -->
        <span class="absolute bottom-2 right-4 text-xs opacity-70">
            ※これはフィクションです
        </span>
    </div>

    <!-- コンテンツ -->
    <div class="max-w-5xl mx-auto px-4 py-12 md:py-16">
        <h2
            class="text-2xl md:text-3xl font-semibold text-emerald-800 mb-6 border-l-4 border-emerald-600 pl-3"
        >
            会社概要
        </h2>

        <div
            class="bg-white shadow-lg ring-1 ring-gray-200 rounded-2xl overflow-hidden"
        >
            <dl class="divide-y divide-gray-200">
                {#each profile as item}
                    <div
                        class="grid grid-cols-1 md:grid-cols-4 hover:bg-emerald-50 transition-colors"
                    >
                        <dt
                            class="bg-gray-50 md:col-span-1 px-4 py-3 font-medium text-gray-600"
                        >
                            {item.label}
                        </dt>
                        <dd class="md:col-span-3 px-4 py-3">{item.value}</dd>
                    </div>
                {/each}
            </dl>
        </div>

        <!-- サマリーカード -->
        <div class="mt-12 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4">
            <div
                class="bg-white rounded-xl shadow ring-1 ring-gray-200 p-3 text-center flex flex-col justify-center"
            >
                <p class="text-sm text-gray-500 m-0">設立</p>
                <p class="text-xl font-bold text-emerald-700 m-0">
                    1957年5月1日
                </p>
            </div>
            <div
                class="bg-white rounded-xl shadow ring-1 ring-gray-200 p-5 text-center"
            >
                <p class="text-sm text-gray-500">資本金</p>
                <p class="text-xl font-bold text-emerald-700">150億円</p>
            </div>
            <div
                class="bg-white rounded-xl shadow ring-1 ring-gray-200 p-5 text-center"
            >
                <p class="text-sm text-gray-500">従業員数</p>
                <p class="text-xl font-bold text-emerald-700">約3,400名</p>
            </div>
            <div
                class="bg-white rounded-xl shadow ring-1 ring-gray-200 p-5 text-center"
            >
                <p class="text-sm text-gray-500">略称</p>
                <p class="text-xl font-bold text-emerald-700">三新／SS鉄道</p>
            </div>
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
