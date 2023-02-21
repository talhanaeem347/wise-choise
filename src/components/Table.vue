<script setup lang="ts">
import { reactive } from 'vue';
import LgTable from './LgTable.vue';
import SmTable from './SmTable.vue';

const head = [
    "Title",
    "Highest Bidder",
    "Auction Time",
    "Highest Bid",
    "Action"
]
const state = reactive({
    tableData: [
        {
            id: 1,
            title: "3D Neon Art - Test Item 7",
            artist: "Sanya",
            category: "Art",
            image: "https://dummyimage.com/200x200",
            bid: {
                rate: 4.20,
                price: 10.30
            },
            bidder: "You",
            auctionTime: "4d : 16h : 12m : 24s",
            action: "Place Bid"
        },
        {
            id: 2,
            title: "3D Neon Art - Test Item 7",
            artist: "Sanya",
            category: "Art",
            image: "https://dummyimage.com/200x200",
            bid: {
                rate: 4.20,
                price: 10.30
            },
            bidder: "Nelly Kutwojk",
            auctionTime: "4d : 16h : 12m : 24s",
            action: "Buy NFT"
        },
        {
            id: 3,
            title: "3D Neon Art - Test Item 7",
            artist: "Sanya",
            category: "Art",
            image: "https://dummyimage.com/200x200",
            bid: {
                rate: 4.20,
                price: 10.30
            },
            bidder: "Peter Grey",
            auctionTime: "4d : 16h : 12m : 24s",
            action: "Buy NFT"
        },
        {
            id: 4,
            title: "3D Neon Art - Test Item 7",
            artist: "Sanya",
            category: "Art",
            image: "https://dummyimage.com/200x200",
            bid: {
                rate: 4.20,
                price: 10.30
            },
            bidder: "Andrew Collects",
            auctionTime: "4d : 16h : 12m : 24s",
            action: "Buy NFT"
        },
        {
            id: 5,
            title: "3D Neon Art - Test Item 7",
            artist: "Sanya",
            category: "Art",
            image: "https://dummyimage.com/200x200",
            bid: {
                rate: 4.20,
                price: 10.30
            },
            bidder: "FAJ NFT Test",
            auctionTime: "4d : 16h : 12m : 24s",
            action: "Buy NFT"
        }
    ]
})
</script>
<template>
    <div class="w-full mx-auto overflow-auto">
        <div class="lg:flex md:flex hidden ">
            <LgTable :tableData="state.tableData" :head="head"/>
        </div>
        <div class="lg:hidden md:hidden flex ">
        <SmTable :tableData="state.tableData"/>
        </div>
    </div>
</template>