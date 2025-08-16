<script lang="ts">
    const ekibenList = [
        {
            name: "ハモ弁（Hamo-ben）",
            price: 880,
            description:
                "都会的でありながら地元の自然や伝統を感じる駅弁。鱧をメインに沿線の特産や季節感を演出。",
            items: [
                "鱧の炙り寿司",
                "信州そばサラダ",
                "季節の煮物",
                "卵焼き（味噌風味）",
                "野沢菜漬け",
                "季節のフルーツ",
            ],
            character: "箸袋・パッケージにやきう（猫）イラスト入り",
            stations: ["浜町駅", "光ヶ丘中央駅", "附属病院前駅", "学文台駅"],
            image: "https://i.imgur.com/slWStq9.png",
        },
        {
            name: "梅（うめ）",
            price: 1600,
            description: "迷ったらこれ！安心感とボリュームのある定番弁当。",
            items: [
                "芋コロッケ",
                "唐揚げ",
                "A5ランクステーキ（ミニ）",
                "エビフライ",
                "しゃけおにぎり",
                "たくあん",
                "ポテチ",
            ],
            image: "https://i.imgur.com/slWStq9.png",
        },
        {
            name: "豪華のり弁（のり弁スペシャル）",
            price: 1330,
            description:
                "ありきたりな「のり弁」を駅弁らしく贅沢アレンジ。旅情と学食感のある一品。",
            items: [
                "焼き飯おにぎり",
                "焼きたて焼売",
                "新鮮アジフライ",
                "国際信州大学の学食味噌汁",
                "チーズハンバーグ",
                "国産ミートボールスパゲティ",
                "しその漬物",
                "たくあん",
            ],
            image: "https://i.imgur.com/slWStq9.png",
        },
        {
            name: "竹 おとなの煮物弁当",
            price: 1000,
            description: "年配層やビジネス客に人気。ほっとする味わい。",
            items: [
                "煮魚",
                "高野豆腐",
                "ひじき煮",
                "野沢菜",
                "梅ごはん",
                "漬物",
            ],
            image: "https://i.imgur.com/slWStq9.png",
        },
    ];

    const souvenirList = [
        "信州りんごゼリー",
        "三蔵名物 みそまんじゅう",
        "焼き芋チップス",
        "国際信州学院オリジナルブレンドコーヒー豆",
        "三新鉄道オリジナルグッズ",
        "地元産ハチミツセット",
        "焼き栗（季節限定）",
        "信州味噌スープ（インスタント）",
    ];
</script>

<!-- ヘッダー / ページタイトル -->
<header class="bg-white/90 backdrop-blur border-b border-emerald-600/40">
    <div class="max-w-6xl mx-auto px-4 py-6 flex items-center gap-4">
        <img
            src="https://i.imgur.com/slWStq9.png"
            alt="岬矢"
            class="h-16 w-auto rounded-lg shadow-md"
        />
        <h1 class="text-3xl font-bold text-emerald-800">岬矢 駅弁販売</h1>
    </div>
    <div
        class="h-1 bg-gradient-to-r from-emerald-600 via-cyan-500 to-emerald-600"
    ></div>
</header>

<main class="max-w-7xl mx-auto px-4 py-12 space-y-12">
    <!-- 駅弁セクション -->
    <section>
        <h2 class="text-3xl font-bold text-emerald-700 text-center mb-8">
            駅弁一覧
        </h2>
        <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-8">
            {#each ekibenList as ekiben}
                <div
                    class="bg-white rounded-2xl shadow-lg overflow-hidden transform hover:scale-105 transition-transform"
                >
                    <div class="relative">
                        <img
                            src="https://i.imgur.com/slWStq9.png"
                            alt="岬矢"
                            class="absolute top-3 left-3 w-auto h-12 rounded-lg shadow-md bg-white p-1 z-10"
                        />
                        <img
                            src={ekiben.image}
                            alt={ekiben.name}
                            class="w-full h-48 object-cover"
                        />
                        <span
                            class="absolute top-3 right-3 bg-emerald-600 text-white text-xs font-semibold px-3 py-1 rounded-full shadow"
                        >
                            {ekiben.price}円
                        </span>
                    </div>
                    <div class="p-5 space-y-3">
                        <h3 class="text-xl font-semibold text-emerald-700">
                            {ekiben.name}
                        </h3>
                        <p class="text-gray-600 text-sm">
                            {ekiben.description}
                        </p>

                        <div>
                            <h4
                                class="text-gray-800 font-semibold mb-1 text-sm"
                            >
                                内容
                            </h4>
                            <ul
                                class="list-disc list-inside text-gray-600 text-sm space-y-1"
                            >
                                {#each ekiben.items as item}
                                    <li>{item}</li>
                                {/each}
                            </ul>
                        </div>

                        {#if ekiben.character}
                            <p class="text-xs italic text-gray-500">
                                キャラクター: {ekiben.character}
                            </p>
                        {/if}

                        {#if ekiben.stations}
                            <div class="mt-2">
                                <h4
                                    class="text-gray-800 font-semibold mb-1 text-sm"
                                >
                                    販売駅
                                </h4>
                                <div class="flex flex-wrap gap-2">
                                    {#each ekiben.stations as s}
                                        <span
                                            class="bg-emerald-100 text-emerald-800 px-2 py-1 rounded-full text-xs"
                                            >{s}</span
                                        >
                                    {/each}
                                </div>
                            </div>
                        {/if}
                    </div>
                </div>
            {/each}
        </div>
    </section>

    <!-- お土産セクション -->
    <section>
        <h2 class="text-3xl font-bold text-emerald-700 text-center mb-8">
            岬矢のお土産
        </h2>
        <div class="grid sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
            {#each souvenirList as s}
                <div
                    class="bg-white rounded-xl shadow p-4 text-center text-sm font-medium text-gray-700 hover:bg-emerald-50 transition-colors"
                >
                    {s}
                </div>
            {/each}
        </div>
    </section>
</main>

<svelte:head>
    <title>駅弁情報 | 三蔵新山株式会社（SS鉄道）</title>
    <meta
        name="description"
        content="三蔵新山株式会社（SS鉄道）の駅弁情報ページ。沿線の人気駅弁や季節限定商品、地元食材を使ったおすすめ駅弁を紹介しています。"
    />
</svelte:head>
