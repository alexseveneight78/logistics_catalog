<template>
  <div>
    <h3>Data Table</h3>
    <app-data-table></app-data-table>
  </div>
</template>

<script>
  import DataTable from './DataTable.vue';
    export default {
        components: {
          'app-data-table': DataTable,
        }
    }
</script>

<style scoped>

</style>
