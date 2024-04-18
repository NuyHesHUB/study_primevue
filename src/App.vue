<template>
  <div>
    <h1>PrimeVue</h1>
    <div class="card">
        <TreeTable :value="nodes">
            <Column field="name" header="Name" expander></Column>
            <Column field="size" header="Size"></Column>
            <Column field="type" header="Type"></Column>
        </TreeTable>
    </div>
  </div>
</template>
<script setup>

import { ref, onMounted } from 'vue';
import { NodeService } from './service/NodeService';
import TreeTable from 'primevue/treetable';
import Column from 'primevue/column';
import 'primevue/resources/themes/aura-light-green/theme.css';

onMounted(() => {
    NodeService.getTreeTableNodes().then((data) => (nodes.value = data));
});

const nodes = ref();
</script>

<style>
  
</style>