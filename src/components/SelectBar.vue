<script setup lang="ts">
import Select from './Select.vue'
import { ref } from 'vue'
let trigerd = ref(false)
const selects = [
    {
        id: 1,
        name: 'Select 1',
        options: [
            { id: 1, name: 'Collectables/Photography' },
            { id: 2, name: 'Option 2' },
            { id: 3, name: 'Option 3' },
        ]
    },
    {
        id: 2,
        name: 'Select 2',
        options: [
            { id: 1, name: 'Lowest to Highest' },
            { id: 2, name: 'Option 2' },
            { id: 3, name: 'Option 3' },
        ]
    },
    {
        id: 3,
        name: 'Select 3',
        options: [
            { id: 1, name: 'All' },
            { id: 2, name: 'Option 2' },
            { id: 3, name: 'Option 3' },
        ]
    }
]
</script>
<template>
    <div class="flex justify-between">
        <div class="w-1/2 lg:flex md:flex  hidden justify-between items-center">
            <Select v-for="select in selects" :options="select.options" class="w-2/5 m-2" />
        </div>
        <div>
            <div class="relative   w-full border m-2 rounded">
                <input type="text" placeholder="Search" id="name" name="name"
                    class="w-full bg-transparent rounded   text-base outline-none  py-1 px-3 leading-8">
                <span
                    class="select-icon absolute right-0 top-0 h-full w-10 text-center pointer-events-none flex items-center justify-center">
                    <i class="fa-solid fa-magnifying-glass"></i>
                </span>
            </div>
            <div :class="trigerd ? 'flex' : 'hidden'" class="w-full flex-col justify-between items-center m-2">
                <Select v-for="select in selects" :options="select.options" class="w-full m-2 " />
            </div>
        </div>
        <div @click="trigerd = !trigerd"
            class="text-rose-500 border m-2 rounded p-2 h-fit border-rose-500 lg:hidden md:hidden">
            <i class="fa-solid fa-filter fa-lg"></i>
        </div>
    </div>
</template>