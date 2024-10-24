<template>
  <div>
    <h2>Sales Chart</h2>
    <BarChart :chart-data="chartData" :options="chartOptions" />
  </div>
</template>

<script>
import { Bar } from 'vue-chartjs';
import { Chart, BarElement, Title, Tooltip, Legend, CategoryScale, LinearScale } from 'chart.js';

Chart.register(BarElement, Title, Tooltip, Legend, CategoryScale, LinearScale);

export default {
  components: {
    BarChart: Bar
  },
  data() {
    return {
      chartData: {
        labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
        datasets: [
          {
            label: 'Sales',
            backgroundColor: '#f87979',
            data: [40, 20, 12, 39, 55, 32, 45]
          }
        ]
      },
      chartOptions: {
        responsive: true,
        maintainAspectRatio: false,
        scales: {
          x: {
            ticks: {
              beginAtZero: true
            }
          },
          y: {
            beginAtZero: true
          }
        }
      }
    };
  }
};
</script>

<style scoped>
h2 {
  margin-top: 20px;
}
</style>