<script setup lang="ts">
defineProps<{
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
    <div class="h-full w-full">
        <div v-for="item in tableData" :key="item.id" class=" p-2 w-full h-1/3 "
            style="border-bottom : 1px solid #2E3A56">
            <div class="">
                <div class="flex p-2 ">
                    <div class="mr-2">
                        <img class="w-32 h-20 rounded" :src="item.image" alt="">
                    </div>
                    <div class="flex flex-col sm:text-lg text-base justify-between items-start">
                        <div class="">
                            {{ item.title }}
                        </div>
                        <div class="">by {{ item.artist }}</div>
                        <button class=" text-sm  px-4 py-1 bg-rose-500">
                            {{ item.category }}
                        </button>
                    </div>
                </div>
            </div>
            <div class="mx-2">
                <div class="flex justify-between ">
                    <div class="">Highest Bid</div>
                    <span>
                        {{ item.bid.rate }} SDX
                        <sub>
                            ({{ item.bid.price }} USD)
                        </sub>
                    </span>
                </div>
                <div class="flex items-center justify-between ">
                    <div>
                        Highest Bidder
                    </div>
                    <button class="my-1  px-4  font-bold p-2  rounded"
                        :class="item.bidder.toLowerCase() == 'you' ? 'bg-green-500' : ''">
                        {{ item.bidder }}
                    </button>
                </div>
                <div class="flex justify-between">
                    <div>
                        Action Time
                    </div>
                    <span>{{ item.auctionTime }} </span>

                </div>
            </div>
            <div class="">
                <div class="w-full flex py-2 text-rose-500">
                    <button class="bg-transparent m-2 border border-rose-500 w-4/5  font-bold p-2  rounded">
                        {{ item.action }}
                    </button>

                    <button class="w-1/5 m-2  rounded border border-rose-500">
                        <i class="fa-solid fa-share-nodes fa-xl"></i>
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>