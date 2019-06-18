<template>
<div class="textcard" key="generaltextcard">
  <div v-if="maintext"><h1>h1{{title}}</h1></div>
  <div v-else><h2>{{title}}</h2></div>
  <p>{{content_text}}</p>
</div>
</template>

<script>
export default {
  name: 'TextCard',
  props: {
    title: String,
    content_text: String,
    maintext: Boolean
    },
}
</script>

