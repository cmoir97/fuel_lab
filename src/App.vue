<template lang="html">
<div>
  <h1>Fuel Usage</h1>

</div>
</template>

<script>
export default {
  data(){
    return {
      data: [],
      organisedData: []
    }
  },
  components: {
    // 'fuel-chart': FuelChart
  },
  methods: {
    organiseData(){
      console.log(this.organisedData.generationmix)
    }
  },
  mounted(){
    fetch('https://api.carbonintensity.org.uk/generation')
    .then(res => res.json())
    .then((fetchedData) => {
      this.data = fetchedData.data.generationmix;
    }
    )
  }
}
</script>

<style lang="css" scoped>
</style>
