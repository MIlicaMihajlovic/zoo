<template>
  <div id="app">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <Zoo />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Zoo from './components/Zoo.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    Zoo
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
