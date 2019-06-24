<template>
  <div id="navbar">
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>
    <router-link to="/highcharts">Highcharts</router-link>
  </div>
</template>

<style lang="sass">
#navbar
  position: sticky
  background-color: #000
  color: #eee
  padding: 1em
  font-size: 1.3em
  // box-shadow: 0px 0px 10px #ff34de

  a
    color: #ddd
    padding: 1em
  
    &:hover
      color: #fff
      text-shadow: 0px 0px 5px #ddd

</style>



