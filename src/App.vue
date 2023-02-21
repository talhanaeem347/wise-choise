<script setup lang="ts">
import SelectBar from './components/SelectBar.vue'
import Table from './components/Table.vue'

</script>
<template>
  <div class="text-white h-screen p-4 overflow-auto" style="background-color: #141A2A;
;" >
    <SelectBar />
    <div style="height: 80vh; ">
      <Table />
    </div>
  </div>
</template>