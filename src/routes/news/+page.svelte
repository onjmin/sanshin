<script lang="ts">
    import { BellIcon, HeartIcon, LeafIcon, UsersIcon } from "@lucide/svelte";

    interface NewsItem {
        title: string;
        content: string[];
        icon?: typeof BellIcon;
        type?: "normal" | "alert";
    }

    const news: NewsItem[] = [
        {
            title: "【三新（SS）鉄道からのお知らせ】",
            type: "alert",
            icon: BellIcon,
            content: [
                "車両を撮影される方は以下のルールをお守りください",
                "① 屋根の上に登る、黄色い線から飛び出るなどの行為は大変危険ですのでお辞めください",
                "② 他のお客様の迷惑になるような行為はお辞めください",
                "③ 上記の行為を発見した場合係員が駆けつけます",
                "危険行為を発見した場合はお近くの通報ボタンでお知らせください",
                "私たちはお客様が快適に使える鉄道会社を目指しております。ご理解よろしくお願いします",
            ],
        },
        {
            title: "環境への配慮",
            icon: LeafIcon,
            content: [
                "駅や車両での省エネルギー化を推進し、CO2排出量削減に取り組んでいます。",
                "緑あふれる駅周辺整備や、花壇・緑地の保全を行い、自然と共生する街づくりを支援。",
            ],
        },
        {
            title: "地域との連携",
            icon: UsersIcon,
            content: [
                "地元の祭りやイベントに積極的に参加し、地域の文化や人と鉄道をつなげています。",
                "地元産品を使った駅弁やお土産を開発し、地域経済の活性化を図っています。",
            ],
        },
        {
            title: "お客様へのやさしさ",
            icon: HeartIcon,
            content: [
                "バリアフリー対応の駅設計やスタッフ研修を行い、誰もが安心して利用できる環境を整備。",
                "快適な乗車環境づくりやサービス向上に日々努めています。",
            ],
        },

        {
            title: "弁当総選挙",
            icon: BellIcon,
            content: ["SNS投票キャンペーンで1位の駅弁を期間限定増量！"],
        },
        {
            title: "やきうパッケージを集めよう",
            icon: BellIcon,
            content: ["全4種集めるとオリジナルステッカー進呈"],
        },
        {
            title: "のり弁なのに豪華すぎキャンペーン",
            icon: BellIcon,
            content: ["SNSで #岬矢ののり弁 をつけて投稿！"],
        },
    ];
</script>

<section class="bg-gray-50 py-12 min-h-screen">
    <div class="max-w-6xl mx-auto px-4">
        <h1 class="text-4xl font-extrabold text-emerald-800 mb-12 text-center">
            「都市と自然を、やさしくむすぶ」三蔵新山株式会社の取り組み
        </h1>

        <div class="space-y-6">
            {#each news as item}
                <div
                    class="rounded-2xl p-6 shadow-lg transition-transform hover:-translate-y-1 hover:shadow-xl
    {item.type === 'alert'
                        ? 'bg-yellow-100 border-2 border-yellow-400'
                        : 'bg-white'}"
                >
                    <h2
                        class="flex items-center gap-3 text-2xl font-semibold mb-4
        {item.type === 'alert' ? 'text-yellow-800' : 'text-emerald-700'}"
                    >
                        {#if item.icon}
                            <svelte:component
                                this={item.icon}
                                class="w-6 h-6"
                            />
                        {/if}
                        {item.title}
                    </h2>
                    <ul class="list-disc list-inside text-gray-700 space-y-2">
                        {#each item.content as line}
                            <li>{line}</li>
                        {/each}
                    </ul>
                </div>
            {/each}
        </div>
    </div>
</section>

<svelte:head>
    <title>ニュース | 三蔵新山株式会社（SS鉄道）</title>
    <meta
        name="description"
        content="三蔵新山株式会社（SS鉄道）の最新ニュースやお知らせ。鉄道運行情報や地域との取り組み、環境への配慮などを掲載しています。"
    />
</svelte:head>
