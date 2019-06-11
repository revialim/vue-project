<template>
  <div>
    <h3>Test picture</h3>
    <img src="../assets/koala_01_hi.png"/>
  </div>
</template>

<script>
export default {
  name: 'PictureStuff',
  props: {
    testprop: String,
    picture_src: String
  },
  // data() {
  //   return {
  //     pict2: '@/src/assets/logo.png'
  //   }
  // }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

a {
  color: #42b983;
}
</style>
