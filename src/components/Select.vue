<script setup lang="ts">
defineProps<{
   options: Array<{ id: number, name: string }> 
}>()
</script>
<template>
    <div class="relative">
        <select
            class="rounded border appearance-none border-gray-300 py-2   text-base pl-3 pr-10 w-full bg-transparent">
            <option v-for="option in options" :key="option.id" class="border" >{{option.name}}</option>
        </select>
        <span
            class="text-rose-500 absolute right-0 top-0 h-full w-10 text-center pointer-events-none flex items-center justify-center">
            <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                class="w-4 h-4" viewBox="0 0 24 24">
                <path d="M6 9l6 6 6-6"></path>
            </svg>
        </span>
    </div>
</template>
<style scoped>

</style>