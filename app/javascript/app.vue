<template>
  <div id="app">
    <p>{{ message }}</p>
       <highcharts :options="chartOptions"></highcharts>
       <highcharts :constructor-type="'stockChart'" :options="chartOptions"></highcharts>
  </div>
</template>

<script>

    import Highcharts from 'highcharts'
    import exportingInit from 'highcharts/modules/exporting'
    import stockInit from 'highcharts/modules/stock'
    import {Chart} from 'highcharts-vue'

    stockInit(Highcharts)

export default {
  data: function () {
    return {
      message: "Hello Vue xxx!",
      chartOptions: {
        chart: {
          type: 'spline'
        },
        title: {
          text: 'Entire title'
        },
        series: [{
          data: [10, 0, 8, 2, 6, 4, 5, 5]
        }]
      },

    }
  },
      components: {
        highcharts: Chart
      }

}
</script>

<style scoped>
p {
  font-size: 2em;
  text-align: center;
}
</style>
