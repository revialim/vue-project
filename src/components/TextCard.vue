<template>
<div class="textcard">
  <h1>{{title}}</h1>
  <p>{{content_text}}</p>
</div>
</template>

<script>
export default {
  name: 'TextCard',
  props: {
    title: String,
    content_text: String
  },
}
</script>

