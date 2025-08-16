<script lang="ts">
    const business = [
        {
            title: "鉄道インフラ事業",
            icon: "🚆",
            description:
                "三蔵新三鉄道の運営、駅・車両の設計・メンテナンス、新規路線の計画・施工管理",
        },
        {
            title: "地域創生・不動産開発事業",
            icon: "🏘️",
            description:
                "駅前開発、地域ブランド支援、ワーケーション拠点開発など地方都市再活性化",
        },
        {
            title: "交通・観光連携サービス",
            icon: "🌄",
            description:
                "観光列車・イベント列車の企画運営、着地型旅行商品、沿線体験プラン提供",
        },
        {
            title: "デジタル・スマートシティ",
            icon: "💡",
            description:
                "スマホ乗車券、混雑予測システム導入、データ活用による地域最適運行",
        },
        {
            title: "広報・文化発信事業",
            icon: "🐱",
            description:
                "マスコットきゃうによるプロモーション、沿線文化・歴史の発信、体験教育イベント",
        },
    ];
</script>

<svelte:head>
    <title>事業紹介 | 三蔵新三株式会社</title>
</svelte:head>

<!-- 企業理念（リデザイン版） -->
<section class="mb-20 bg-gray-50 py-16">
    <div class="max-w-5xl mx-auto px-6">
        <!-- タイトル -->
        <div class="text-center mb-12">
            <div
                class="inline-flex items-center justify-center bg-emerald-100 rounded-full px-4 py-2 mb-4"
            >
                <span class="text-3xl mr-2 animate-spin-slow">🎯</span>
                <h2
                    class="text-3xl md:text-4xl font-extrabold text-emerald-800"
                >
                    企業理念
                </h2>
            </div>
            <p class="text-gray-700 text-lg md:text-xl max-w-3xl mx-auto">
                「つなぐ、育てる、ひらく。」三蔵新三株式会社は、地域・人・未来を結ぶ架け橋となり、
                ともに歩み、持続可能で魅力ある社会を共創します。
            </p>
        </div>

        <!-- カード型ボックスで目立たせる -->
        <div class="grid md:grid-cols-3 gap-6">
            <div
                class="bg-white rounded-2xl shadow-lg p-6 text-center hover:scale-105 transition-transform"
            >
                <div class="text-emerald-600 text-4xl mb-4">🌱</div>
                <h3 class="font-bold text-lg mb-2">つなぐ</h3>
                <p class="text-gray-600 text-sm">
                    地域と人をつなぎ、交通インフラで未来を結びます。
                </p>
            </div>
            <div
                class="bg-white rounded-2xl shadow-lg p-6 text-center hover:scale-105 transition-transform"
            >
                <div class="text-emerald-600 text-4xl mb-4">⚙️</div>
                <h3 class="font-bold text-lg mb-2">育てる</h3>
                <p class="text-gray-600 text-sm">
                    社会・地域・文化を育む取り組みを推進します。
                </p>
            </div>
            <div
                class="bg-white rounded-2xl shadow-lg p-6 text-center hover:scale-105 transition-transform"
            >
                <div class="text-emerald-600 text-4xl mb-4">🌟</div>
                <h3 class="font-bold text-lg mb-2">ひらく</h3>
                <p class="text-gray-600 text-sm">
                    新しい価値と可能性を開き、未来を切り拓きます。
                </p>
            </div>
        </div>
    </div>
</section>

<!-- 事業内容カードグリッド -->
<section class="mb-16">
    <h2 class="text-3xl font-bold text-emerald-700 mb-8 text-center">
        🚆 主な事業内容
    </h2>
    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        {#each business as b}
            <div
                class="bg-white rounded-2xl p-6 shadow-md hover:shadow-xl transition-all hover:-translate-y-1 hover:scale-105"
            >
                <div class="text-4xl mb-4">{b.icon}</div>
                <h3 class="text-xl font-semibold mb-2">{b.title}</h3>
                <p class="text-gray-600 leading-relaxed">{b.description}</p>
            </div>
        {/each}
    </div>
</section>
