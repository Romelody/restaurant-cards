<template>
  <div id="app">
    <Restaurants msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import Restaurants from './components/Restaurants.vue'

export default {
  name: 'App',
  components: {
    Restaurants
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
*{
  box-sizing: border-box;

}
</style>
