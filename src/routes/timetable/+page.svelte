<script lang="ts">
    const timetable = [
        {
            station: "浜町",
            times: ["06:00", "06:30", "07:00", "07:30", "08:00", "08:30"],
        },
        {
            station: "新原",
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
            station: "光ヶ丘中央",
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
            運行時間表
        </h1>
        <p class="text-gray-700 mb-8">
            主な駅の始発から午前8:30までの運行時間です。
        </p>

        <div class="overflow-x-auto bg-white shadow-lg rounded-2xl">
            <table class="min-w-full divide-y divide-gray-200 text-center">
                <thead class="bg-emerald-700 text-white">
                    <tr>
                        {#each headers as header}
                            <th class="px-4 py-2 text-sm font-medium"
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
                                class="px-4 py-2 font-medium text-left text-emerald-800"
                                >{row.station}</td
                            >
                            {#each row.times as time}
                                <td class="px-4 py-2">{time}</td>
                            {/each}
                        </tr>
                    {/each}
                </tbody>
            </table>
        </div>
    </div>
</section>

<svelte:head>
    <title>運行時間 | 三蔵新山株式会社</title>
    <meta
        name="description"
        content="三蔵新山株式会社（SS鉄道）の運行時間表。主要駅の始発から午前中までの時刻を掲載しています。"
    />
</svelte:head>
