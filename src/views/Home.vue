<template>
  <div class="home">
    <Header/>
    This is home
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '../components/Header.vue'

export default {
  name: 'home',
  components: {
    Header
  }
}
</script>
