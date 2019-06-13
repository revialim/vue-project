<template>
  <div>
    <img src="../assets/koala_01_hi.png"/>
    <div class="pic_sub">some picture description lorem ipsum</div>
  </div>
</template>

<script>
export default {
  name: 'PictureCard',
  props: {
    picture_src: String
  }
}
</script>

<style lang="sass" scoped>
.pic_sub
  font-size: 0.8em
  color: #444
</style>
