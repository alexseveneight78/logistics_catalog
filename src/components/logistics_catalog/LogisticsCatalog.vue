<template>
  <div>
    <h3>Data Table</h3>
    <button @click="addData">Add Data</button>
    <app-add-data v-if="addDataStatus"></app-add-data>
    <app-data-table></app-data-table>
  </div>
</template>

<script>
  import DataTable from './DataTable.vue';
  import AddData from './AddData.vue';
    export default {
        components: {
          'app-data-table': DataTable,
          'app-add-data': AddData
        },
        data(){
          return {
            addDataStatus: false
          }
        },
      methods: {
          addData(){
            this.addDataStatus = true;
          }
      }
    }
</script>

<style scoped>

</style>
