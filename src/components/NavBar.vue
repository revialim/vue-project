<template>
  <div id="navbar">
    <a href="#home">Home</a>
    <a href="#some">Some</a>
    <a href="#where">Where</a>
    <a href="#about">About</a>
    <a href="#contact">Contact</a>
  </div>
</template>

<script>
export default {
  
}
</script>

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



