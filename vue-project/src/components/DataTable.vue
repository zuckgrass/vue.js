<template>
    <div>
      <h2>Data Table</h2>
      <table>
        <thead>
          <tr>
            <th>Product</th>
            <th>Quantity</th>
            <th>Price</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(item, index) in items" :key="index">
            <td>{{ item.product }}</td>
            <td>{{ item.quantity }}</td>
            <td>{{ item.price }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        items: [
          { product: 'Laptop', quantity: 10, price: '$1000' },
          { product: 'Keyboard', quantity: 25, price: '$50' },
          { product: 'Monitor', quantity: 5, price: '$300' }
        ]
      }
    }
  }
  </script>
  
  <style scoped>
  table {
    margin: 0 auto;
    border-collapse: collapse;
  }
  table, th, td {
    border: 1px solid black;
  }
  th, td {
    padding: 8px;
  }
  </style>
  