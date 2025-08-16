<script lang="ts">
    const profile: { label: string; value: string }[] = [
        { label: "社名", value: "三蔵新山株式会社（Sanzō‑Shinzan Co., Ltd.）" },
        { label: "略称", value: "三新（さんしん）、SS鉄道" },
        { label: "本社所在地", value: "東京都文京区三山町1-45（架空住所）" },
        { label: "設立", value: "1957年（昭和32年）5月1日" },
        { label: "資本金", value: "150億円（非上場）" },
        { label: "代表取締役社長", value: "新山透（しんざん とおる）" },
        { label: "従業員数", value: "約3,400名（グループ全体）" },
        { label: "スローガン", value: "「都市と自然を、やさしくむすぶ」" },
    ];
</script>

<section class="relative overflow-hidden">
    <div
        class="absolute inset-0 -z-10 opacity-30 pointer-events-none select-none"
    >
        <div
            class="absolute -top-24 -left-24 w-72 h-72 rounded-full bg-emerald-200 blur-3xl"
        ></div>
        <div
            class="absolute -bottom-24 -right-24 w-72 h-72 rounded-full bg-cyan-200 blur-3xl"
        ></div>
    </div>

    <div class="max-w-5xl mx-auto px-4 py-12 md:py-16">
        <h1 class="text-3xl md:text-4xl font-bold tracking-tight mb-2">
            会社概要
        </h1>
        <p class="text-gray-600 mb-8">
            Sanzō‑Shinzan Co., Ltd.（略称：三新／SS鉄道）の基本情報です。
        </p>

        <div
            class="bg-white shadow-sm ring-1 ring-gray-200 rounded-2xl overflow-hidden"
        >
            <dl class="divide-y divide-gray-200">
                {#each profile as item}
                    <div class="grid grid-cols-1 md:grid-cols-4">
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

        <!-- 補足情報（任意）：カードでサマリー表示 -->
        <div class="mt-10 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4">
            <div class="bg-white rounded-2xl ring-1 ring-gray-200 p-4">
                <p class="text-xs text-gray-500">設立</p>
                <p class="text-lg font-semibold">1957年5月1日</p>
            </div>
            <div class="bg-white rounded-2xl ring-1 ring-gray-200 p-4">
                <p class="text-xs text-gray-500">資本金</p>
                <p class="text-lg font-semibold">150億円</p>
            </div>
            <div class="bg-white rounded-2xl ring-1 ring-gray-200 p-4">
                <p class="text-xs text-gray-500">従業員数</p>
                <p class="text-lg font-semibold">約3,400名</p>
            </div>
            <div class="bg-white rounded-2xl ring-1 ring-gray-200 p-4">
                <p class="text-xs text-gray-500">略称</p>
                <p class="text-lg font-semibold">三新／SS鉄道</p>
            </div>
        </div>
    </div>
</section>

<svelte:head>
    <title>会社概要 | 三蔵新山株式会社</title>
    <meta
        name="description"
        content="三蔵新山株式会社（Sanzō‑Shinzan Co., Ltd.）の会社概要。設立、資本金、所在地、代表者、従業員数などの基本情報。"
    />
</svelte:head>
