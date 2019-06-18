<template>
  <div>
    <img :src="resolve_img_url(picture_src)" />

    <div class="pic_sub">{{pic_desc}}</div>
  </div>
</template>

<script>
export default {
  
  name: 'PictureCard',
  props: {
    picture_src: String,
    pic_desc: String
  },
  methods: {
    resolve_img_url: function (path) {
      let images = require.context('../assets/', false, /\.png$|\.jpg$/)
      return images("./"+path)
    }
  }
}
</script>

<style lang="sass" scoped>
img
  max-width: 35vw
  max-height: 45vh

.pic_sub
  font-size: 0.8em
  color: #444
</style>
