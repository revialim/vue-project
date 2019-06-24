<template>
  <div class="highcharts">
    <ChartCard/>
  </div>
</template>

<script>
// @ is an alias to /src
import ChartCard from '../components/ChartCard.vue'

export default {
  name: 'home',
  components: {
    ChartCard
  }
}
</script>