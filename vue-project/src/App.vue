<template>
  <div id="app">
    <h1>Tecsys Dashboard</h1>
    <DataTable />
    <Chart />
    <SalesVolumeChart />
  </div>
</template>

<script>
import DataTable from './components/DataTable.vue'
import Chart from './components/SalesChart.vue'
import SalesVolumeChart from './components/SalesVolumeChart.vue';

export default {
  name: 'App',
  components: {
    DataTable,
    Chart,
    SalesVolumeChart
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  margin: 20px;
}
</style>