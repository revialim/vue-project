<template>
  <div id="app">
    <NavBar/>
    <Header/>

    <ChartCard />
    
    <TextCard v-bind:maintext=true title="Some H1 Title Lorem" content_text="Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
      sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
      Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris 
      nisi ut aliquip ex ea commodo consequat. 
      Duis aute irure dolor in reprehenderit in voluptate 
      velit esse cillum dolore eu fugiat nulla pariatur. 
      Excepteur sint occaecat cupidatat non proident, 
      sunt in culpa qui officia deserunt mollit anim id est laborum."/>
    
    <TextCard v-bind:maintext=false title="some h2 title test" content_text="Duis aute irure dolor in reprehenderit in voluptate 
      velit esse cillum dolore eu fugiat nulla pariatur." />

    <PictureCard pic_desc="some picture description png" picture_src='orange.png'/>
    <PictureCard pic_desc='some picture description jpg' picture_src='sunset.jpg'/>

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
import ChartCard from './components/ChartCard.vue'

export default {
  name: 'app',
  components: {
    PictureCard,
    TodoList,
    NavBar,
    Header,
    TextCard,
    ChartCard
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
