//background_img.jpg

<template>
  <div class="header">
    <div class="bg_overlay">
      <h2>Header Title Lorem Ipsum</h2>
    </div>
  </div>
</template>

<script>
export default {
  
}
</script>

<style lang="sass" scoped>
.header
  width: 100vw
  height: 75vh
  background-image: url('../assets/background_img.jpg')

  .bg_overlay
    width: inherit
    height: inherit
    background-color: rgba(0,0,0,0.3)

  h2
    width: 50%
    margin: auto
    text-align: center
    color: #eee
    padding-top: 33vh
    


</style>

