<script setup lang="ts">
defineProps<{
    head: Array<string>,
    tableData: Array<{
        id: number,
        title: string,
        artist: string,
        category: string,
        image: string,
        bid: {
            rate: number,
            price: number
        },
        bidder: string,
        auctionTime: string,
        action: string
    }>
}>()
</script>
<template>
    <table class="table-auto w-full text-left whitespace-no-wrap">
        <thead class="">
            <tr class="bg-slate-700  ">
                <th v-for="(item, index) in head" class="px-4 py-3 title-font  font-medium  text-sm"
                    :class="index == 0 ? 'w-2/6' : 'w-1/6'">
                    <div class="flex">{{ item }}</div>
                </th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="item in tableData" :key="item.id" class="h-32 p-2 m-2 border-b"
                style="border: 1px solid #2E3A56">
                <td class="">
                    <div class="flex">
                        <div class="m-1">
                            <img class="w-32 h-24 rounded" :src="item.image" alt="">
                        </div>
                        <div class="m-1 flex flex-col justify-between items-start">
                            <div class="text-xl">
                                {{ item.title }}
                            </div>
                            <div class="text-lg">by {{ item.artist }}</div>
                            <button class=" px-4 py-1 bg-rose-500">
                                {{ item.category }}
                            </button>
                        </div>
                    </div>
                </td>
                <td class="">
                    <div class="flex items-center justify-center ">
                        <button class="m-2  px-4  font-bold p-2  rounded"
                            :class="item.bidder.toLowerCase() == 'you' ? 'bg-green-500' : ''">
                            {{ item.bidder }}
                        </button>
                    </div>
                </td>
                <td class="">
                    <div class="flex justify-center">
                        <span>{{ item.auctionTime }} </span>

                    </div>
                </td>
                <td class="">
                    <div class="flex justify-center">
                        <span>
                            {{ item.bid.rate }} SDX
                            <sub>
                                ({{ item.bid.price }} USD)
                            </sub>
                        </span>
                    </div>
                </td>
                <td class="">
                    <div class="w-full flex py-2 text-rose-500">
                        <button class="bg-transparent m-2 border border-rose-500 w-3/5  font-bold p-2  rounded">
                            {{ item.action }}
                        </button>

                        <button class="w-1/5 m-2  rounded border border-rose-500">
                            <i class="fa-solid fa-share-nodes fa-xl"></i>
                        </button>
                    </div>
                </td>
            </tr>
        </tbody>
    </table>
</template>