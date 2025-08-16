<script lang="ts">
    const timetable = [
        {
            station: "華町",
            times: ["06:00", "06:30", "07:00", "07:30", "08:00", "08:30"],
        },
        {
            station: "旧原",
            times: ["06:10", "06:40", "07:10", "07:40", "08:10", "08:40"],
        },
        {
            station: "国際信州学院大学前",
            times: ["06:20", "06:50", "07:20", "07:50", "08:20", "08:50"],
        },
        {
            station: "山田教授私邸前",
            times: ["06:30", "07:00", "07:30", "08:00", "08:30", "09:00"],
        },
        {
            station: "闇ヶ丘中央",
            times: ["06:40", "07:10", "07:40", "08:10", "08:40", "09:10"],
        },
    ];

    const headers = ["駅名", "6:00", "6:30", "7:00", "7:30", "8:00", "8:30"];
</script>

<section class="bg-emerald-50 min-h-screen py-12">
    <div class="max-w-6xl mx-auto px-4">
        <h1
            class="text-3xl md:text-4xl font-bold text-emerald-800 mb-6 border-l-4 border-emerald-600 pl-3"
        >
            電車の時刻と路線図
        </h1>
        <p class="text-gray-700 mb-8">
            朝の電車の時刻や路線マップをまとめています。お出かけ前にチェックしてください。
        </p>

        <!-- 路線図（横並び） -->
        <div class="flex flex-col md:flex-row gap-6 mb-6">
            <div class="flex-1 min-w-[300px]">
                <h2 class="text-lg font-semibold text-emerald-700 mb-2">
                    路線マップ（横長）
                </h2>
                <img
                    src="https://i.imgur.com/Wye9nsN.png"
                    alt="横方向路線図"
                    class="rounded-xl shadow-lg border border-gray-200 w-full object-contain"
                />
            </div>
            <div class="flex-1 min-w-[300px]">
                <h2 class="text-lg font-semibold text-emerald-700 mb-2">
                    三蔵新三鉄道のレトロ車両、マルタ96
                </h2>
                <img
                    src="https://i.imgur.com/gnxdDLE.jpeg"
                    alt="三蔵新三鉄道のレトロ車両、マルタ96"
                    class="rounded-xl shadow-lg border border-gray-200 w-full object-contain"
                />
            </div>
        </div>

        <!-- 運行時刻表 -->
        <div class="overflow-x-auto bg-white shadow-lg rounded-2xl">
            <table class="min-w-full divide-y divide-gray-200 text-center">
                <thead class="bg-emerald-700 text-white rounded-t-2xl">
                    <tr>
                        {#each headers as header}
                            <th
                                class="px-6 py-3 text-sm font-medium rounded-t-lg"
                                >{header}</th
                            >
                        {/each}
                    </tr>
                </thead>
                <tbody class="divide-y divide-gray-200">
                    {#each timetable as row, i}
                        <tr
                            class="hover:bg-emerald-50 transition-colors {i %
                                2 ===
                            0
                                ? 'bg-gray-50'
                                : ''}"
                        >
                            <td
                                class="px-6 py-3 font-medium text-left text-emerald-800"
                                >{row.station}</td
                            >
                            {#each row.times as time}
                                <td class="px-6 py-3">{time}</td>
                            {/each}
                        </tr>
                    {/each}
                </tbody>
            </table>
        </div>
    </div>
</section>

<svelte:head>
    <title>電車の時刻と路線図 | 三蔵新山株式会社</title>
    <meta
        name="description"
        content="三蔵新山株式会社（SS鉄道）の路線マップと電車の時刻。朝の主要駅の運行情報を掲載しています。"
    />
</svelte:head>
