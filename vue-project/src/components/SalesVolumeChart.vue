<template>
    <div>
      <h2>Sales Volume Chart</h2>
      <div class="chart-container">
        <BarChart :chart-data="chartData" :options="chartOptions" />
      </div>
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
              label: 'Sales Volume',
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
              title: {
                display: true,
                text: 'Months'
              },
              beginAtZero: true
            },
            y: {
              title: {
                display: true,
                text: 'Sales Volume'
              },
              beginAtZero: true
            }
          }
        }
      };
    },
    mounted() {
      console.log('chartData:', this.chartData);
    }
  };
  </script>
  
  <style scoped>
  h2 {
    margin-top: 20px;
  }
  .chart-container {
    position: relative;
    height: 400px; /* Set a height for the chart */
    width: 100%;
  }
  </style>
  