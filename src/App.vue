<template lang="html">
<div>
  <h1>Fuel Usage</h1>
  <h1>{{organisedData}}</h1>
  <fuel-chart :organisedData="organisedData"></fuel-chart>
</div>
</template>

<script>
import FuelChart from './components/FuelChart.vue'

export default {
  data(){
    return {
      data: [],
      organisedData: null
    }
  },
  components: {
    "fuel-chart": FuelChart
  },
  mounted(){
    fetch('https://api.carbonintensity.org.uk/generation')
    .then(res => res.json())
    .then((fetchedData) => {
      this.data = fetchedData.data.generationmix
      let mappedObj = this.data.map((obj) => Object.values(obj))
      mappedObj.unshift(["fuel", "percentage"]);
      this.organisedData = mappedObj
    }
    )
  }
}
</script>

<style lang="css" scoped>
</style>
