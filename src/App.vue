<template>
  <div id="app">
    <NavBar/>
    <Header/>

    <TextCard title="Some H1 Title Lorem" content_text="Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
      sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
      Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris 
      nisi ut aliquip ex ea commodo consequat. 
      Duis aute irure dolor in reprehenderit in voluptate 
      velit esse cillum dolore eu fugiat nulla pariatur. 
      Excepteur sint occaecat cupidatat non proident, 
      sunt in culpa qui officia deserunt mollit anim id est laborum."/>
    

    <PictureCard testprop="testprop content haha" picture_src="../assets/logo.png"/>

    <input v-model="username" placeholder="your name">

    <p>Welcome {{username}} </p>

    <TodoList/>

  </div>
</template>

<script>
import PictureCard from './components/PictureCard.vue'
import TodoList from './components/TodoList.vue'
import NavBar from './components/NavBar.vue'
import Header from './components/Header.vue'
import TextCard from './components/TextCard.vue'

export default {
  name: 'app',
  components: {
    // HelloWorld,
    PictureCard,
    TodoList,
    NavBar,
    Header,
    TextCard
  },
  data() {
    return {
      testvar: 'test ',
      username: ''
    }
  }
}
</script>

<style lang="sass">
#app
  font-family: 'Avenir', Helvetica, Arial, sans-serif
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  /* text-align: center; */
  color: #2c3e50
  /* margin-top: 60px; */
  margin: 0
  
  h1
    margin-top: 0
</style>
