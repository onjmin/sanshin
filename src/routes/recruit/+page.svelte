<script lang="ts">
    import {
        ClockIcon,
        ClipboardListIcon,
        MailIcon,
        CircleDollarSignIcon,
    } from "@lucide/svelte";

    const recruitment = {
        year: 2025,
        number: 94,
        倍率: 200,
        shift: [
            { label: "早朝", time: "4:30〜9:00", note: "通勤客・始発対応" },
            { label: "朝番", time: "6:00〜14:00" },
            { label: "昼番", time: "11:00〜17:00" },
            {
                label: "遅番",
                time: "17:00〜24:00",
                note: "観光客・夜行列車対応",
            },
        ],
        hourlyWage: "946円〜",
        benefits: ["交通費支給", "制服貸与", "昇給あり", "日祝手当別途支給"],
        locations: ["浜町駅", "光ヶ丘中央駅", "岬ヶ浦駅"],
        jobDetails: [
            "駅弁・お土産品の販売・レジ業務",
            "品出し・陳列",
            "観光案内の簡単な対応",
        ],
        notes: [
            "希望に合わせたシフト調整可",
            "学生・フリーター・主婦（夫）歓迎",
            "Wワーク・扶養内勤務も相談OK",
        ],
        contact: `店頭か<a href="mailto:onjmin931@gmail.com?subject=釣りだよ" class="text-blue-600 underline">メール</a>でご連絡ください。`,
        message:
            "長時間シフトを支えるスタッフを大募集。待遇・環境充実で働きやすさも◎",
    };

    const cards = [
        {
            title: "勤務時間（シフト制）",
            icon: ClockIcon,
            color: "from-cyan-50 to-emerald-50",
            content: recruitment.shift.map(
                (s) =>
                    s.label + "：" + s.time + (s.note ? `（${s.note}）` : ""),
            ),
            notes: recruitment.notes,
        },
        {
            title: "給与・勤務地",
            icon: CircleDollarSignIcon,
            color: "from-yellow-50 to-yellow-100",
            content: [
                `💰 時給：${recruitment.hourlyWage}（${recruitment.benefits.join("・")}）`,
                `📍 勤務地：${recruitment.locations.join("・")}`,
            ],
        },
        {
            title: "お仕事内容",
            icon: ClipboardListIcon,
            color: "from-pink-50 to-pink-100",
            content: recruitment.jobDetails,
        },
        {
            title: "応募方法",
            icon: MailIcon,
            color: "from-purple-50 to-purple-100",
            content: [recruitment.contact, recruitment.message],
            isNote: true,
        },
    ];
</script>

<svelte:head>
    <title>岬矢 売店スタッフ求人 | 三蔵新山株式会社（SS鉄道）</title>
    <meta
        name="description"
        content="岬矢の駅弁・お土産売店スタッフ求人ページ。シフト制で学生・主婦歓迎。勤務地は沿線各駅。応募方法も掲載。"
    />
</svelte:head>

<main class="max-w-6xl mx-auto px-4 py-12 space-y-12">
    <!-- 採用概要 -->
    <section class="text-center space-y-2">
        <h2 class="text-4xl font-bold text-emerald-700">2025年採用情報</h2>
        <p class="text-gray-700 text-lg">
            採用人数: <strong>{recruitment.number}人</strong> | 採用倍率:
            <strong>{recruitment.倍率}倍</strong>
        </p>
    </section>

    <!-- 情報カード -->
    <section class="grid sm:grid-cols-2 gap-8">
        {#each cards as card}
            <div
                class={`bg-gradient-to-br ${card.color} rounded-3xl shadow-xl p-8 transform hover:-translate-y-2 hover:shadow-2xl transition-transform`}
            >
                <!-- アイコンをフロー内に配置 -->
                <div class="flex justify-center mb-4">
                    <svelte:component
                        this={card.icon}
                        class="w-10 h-10 text-gray-700"
                    />
                </div>

                <h3
                    class="text-xl font-semibold text-gray-800 text-center mb-4"
                >
                    {card.title}
                </h3>

                <ul
                    class="list-disc list-inside text-gray-700 space-y-1 text-sm"
                >
                    {#each card.content as line}
                        <li>{line}</li>
                    {/each}
                </ul>

                {#if card.notes}
                    <ul
                        class="list-inside text-green-700 space-y-1 mt-2 text-sm"
                    >
                        {#each card.notes as note}
                            <li>✅ {note}</li>
                        {/each}
                    </ul>
                {/if}

                {#if card.isNote}
                    <p
                        class="mt-2 text-gray-600 italic border-l-4 border-purple-400 pl-3"
                    >
                        {@html card.content[0]}
                    </p>
                    <p
                        class="mt-2 text-gray-600 italic border-l-4 border-purple-400 pl-3"
                    >
                        {card.content[1]}
                    </p>
                {/if}
            </div>
        {/each}
    </section>
</main>
