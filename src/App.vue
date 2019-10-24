<template lang="html">
<div>
  <h1>Fuel Usage</h1>

</div>
</template>

<script>
export default {
  data(){
    return {
      fetchedData: [],
      organisedData: []
    }
  },
  components: {
    // 'fuel-chart': FuelChart
  },
  methods: {
    organiseData(){
      console.log("hi")
    }
  },
  mounted(){
    this.organiseData()
    fetch('https://api.carbonintensity.org.uk/generation')
    .then(res => res.json())
    .then(fetchedData => this.fetchedData = fetchedData)
  }
}
</script>

<style lang="css" scoped>
</style>
