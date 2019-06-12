<template>
  <div id="app">
    <NavBar/>
    <Header/>
    
    <h1>Home</h1>
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <PictureStuff testprop="testprop content haha" picture_src="../assets/logo.png"/>

    <input v-model="username" placeholder="your name">

    <p>Welcome {{username}} </p>

    <TodoList/>

  </div>
</template>

<script>
import PictureStuff from './components/PictureStuff.vue'
import TodoList from './components/TodoList.vue'
import NavBar from './components/NavBar.vue'
import Header from './components/Header.vue'

export default {
  name: 'app',
  components: {
    // HelloWorld,
    PictureStuff,
    TodoList,
    NavBar,
    Header
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
