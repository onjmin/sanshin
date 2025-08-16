<script lang="ts">
    import { writable } from "svelte/store";

    interface Voice {
        type: "感想" | "批評";
        name: string;
        age?: string;
        occupation?: string;
        location?: string;
        text: string;
    }

    const voices: Voice[] = [
        {
            type: "感想",
            name: "30代・会社員",
            location: "東京都世田谷区",
            text: "通勤で毎日SS鉄道を利用しています。ダイヤの正確さと、車内の清潔感にはいつも感心しています。都心と郊外を結ぶ路線として、なくてはならない存在です。",
        },
        {
            type: "感想",
            name: "40代・観光客",
            location: "大阪府在住",
            text: "東京観光の際にSS鉄道を使いました。車窓から見える緑豊かな景色が印象的で、まるで小旅行気分でした。観光案内も充実していて、初めてでも安心して乗れました。",
        },
        {
            type: "感想",
            name: "50代・フリーランス",
            location: "埼玉県在住",
            text: "沿線の開発と環境保全を両立している姿勢に共感しています。『都市と自然を、やさしくむすぶ』というスローガン、そのままだと思います。",
        },
        {
            type: "感想",
            name: "10代・高校生",
            location: "東京都北区",
            text: "SS鉄道のキャラクターが可愛くて好きです！駅のスタンプ集めも楽しくて、友達とよく出かけます。",
        },
        {
            type: "感想",
            name: "60代・男性",
            text: "女性専用車両に入った途端、素晴らしい女子高生の汗とムワッとしたナニカが匂ってきた。部活帰りの女子高生が多かった。とても良い体験でした！世間では批判があるでしょうけど、専用車両をもっと増やすbきです！",
        },
        {
            type: "批評",
            name: "30代・女性",
            text: "女性専用車両に乗っていたら50歳位のはげた男が乗ってきました。本当に迷惑です。",
        },
        {
            type: "批評",
            name: "50代・男性",
            text: "電車に乗ったらなぜかおばさんに怒られました。今も理不尽すぎて怒りが収まりません",
        },
        {
            type: "批評",
            name: "40代・男性・会社員",
            text: "駅のトイレに入ろうとしたら、3つある個室のうち2つが「使用禁止」の張り紙。残り1つに長蛇の列。毎朝これでは用を足す前に電車に遅れます。修理はいつ終わるのでしょうか。",
        },
        {
            type: "批評",
            name: "80代・男性",
            text: "この駅のトイレがうち２つも故障していた。これでは電車に間に合わないと思い、駅のホームにて大便と小便をしたところ、近くにいた駅員に蹴り飛ばされ私は気がついたら病院のベットの上にいた。大便をしている最中に意識を失ったので、病院のベッドでも続けて脱糞してしまった。恥ずかしい思いをしました。駅員を許せません。",
        },
        {
            type: "批評",
            name: "50代・男性・自営業",
            text: "駅の自動改札に切符を入れたら、なぜか「ピンポーン！」と大音量で拒否され、後ろにいた人たちから冷たい視線。駅員を呼んだら「あ、それ昨日の切符ですね」と鼻で笑われました。昨日？　たった数時間前に買った切符がもうゴミですか。時空の歪みでも起きてるのでしょうか。",
        },
        {
            type: "批評",
            name: "30代・男性",
            text: "ホームレスが邪魔で写真が撮れない！",
        },
        {
            type: "批評",
            name: "35歳・会社員",
            text: "マルタ96の電車はデザインが良くて快適なのは助かります。ただ、ラッシュ時の混雑がひどく、もう少し改善してほしいです。",
        },
        {
            type: "感想",
            name: "40代・女性",
            text: "子供が安心してトイレできる環境で助かりました！",
        },
        {
            type: "批評",
            name: "60代・女性",
            text: "優先席の前に立っても譲らない人がおり、さらに優先席の数も少ないので仕方なく吊り革を使うしかありません。さらに吊り革も少なく不便と感じます",
        },
        {
            type: "批評",
            name: "60代・男性・会社員",
            text: "駅のトイレがリニューアルされたと聞き、期待して入ったら有料式に変わっていました。10円や20円ならまだしも、なんと100円。清潔さも特別良いわけではなく、ただの小遣い稼ぎにしか見えません。",
        },
        {
            type: "批評",
            name: "40代・男性",
            text: "利用者数に対して改札が少なく、ホームが狭いと感じます。この前通勤ラッシュの時間に人が押し寄せ、財布とイヤホンを落としてしまいました。この混雑をしっかり整備してほしいです",
        },
        {
            type: "感想",
            name: "20代・男性",
            text: "この前、華町で線路内に落とし物をしてしまったのですが、すぐに物を拾ってくれて助かりました。おかげで大事な会議に間に合いました。拾ってくれた駅員さんの対応もとても親切で丁寧で安心しました。",
        },
        {
            type: "感想",
            name: "10代・男性",
            text: "通学中、電車内で失禁をしてしまったのですが駅員さんがすぐにオムツを持ってきてくれました。とても親切な方々です。",
        },
        {
            type: "感想",
            name: "0代・男性",
            text: "ばぶばぶーばぶばぶー",
        },
    ];

    const openIndexes = writable<number[]>([]);

    function toggle(index: number) {
        openIndexes.update((arr) =>
            arr.includes(index)
                ? arr.filter((i) => i !== index)
                : [...arr, index],
        );
    }
</script>

<section class="bg-emerald-50 py-12">
    <div class="max-w-6xl mx-auto px-4">
        <h2 class="text-3xl font-bold text-emerald-700 mb-2 text-center">
            利用者の声
        </h2>

        <!-- 高さを固定してスクロール可能に -->
        <div
            class="bg-white rounded-xl shadow ring-1 ring-gray-200 h-[500px] overflow-y-auto p-4"
        >
            <ul class="space-y-3">
                {#each voices as v, i}
                    <li class="border-b border-gray-200 pb-2 last:border-b-0">
                        <div class="flex justify-between items-start">
                            <div>
                                <p class="font-semibold text-gray-800">
                                    {v.name}{v.age
                                        ? ` (${v.age})`
                                        : ""}{v.occupation
                                        ? `・${v.occupation}`
                                        : ""}
                                </p>
                                {#if v.location}
                                    <p class="text-gray-500 text-sm">
                                        {v.location}
                                    </p>
                                {/if}
                            </div>
                            <span
                                class="text-xs px-2 py-1 rounded-full {v.type ===
                                '感想'
                                    ? 'bg-emerald-100 text-emerald-800'
                                    : 'bg-red-100 text-red-700'}"
                            >
                                {v.type}
                            </span>
                        </div>
                        <p class="text-gray-700 text-sm mt-1">{v.text}</p>
                    </li>
                {/each}
            </ul>
        </div>

        <p class="text-center text-gray-500 text-sm mb-6 my-3">
            駅舎で実施したアンケートにご協力いただいた皆さまの声を掲載しています。
        </p>
    </div>
</section>
