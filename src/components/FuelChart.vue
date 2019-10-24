<template lang="html">
  <div id="app" v-if="organisedData">
    <GChart
       type="ColumnChart"
       :data="organisedData"
       :options="chartOptions"
     />
  </div>
</template>

<script>
import { GChart } from "vue-google-charts";

export default {
  name: "fuel-chart",
  props: ["organisedData"],
  data () {
    return {
      chartOptions: {
        chart: {
          title: 'Fuel Type Usage Rates',
          subtitle: 'Over Selected Timeframe',
        }
      }
    }
  },
}
</script>

<style lang="css" scoped>
</style>
