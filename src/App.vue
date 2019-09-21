<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<script>
import Index from './components/Index.vue'
import Login from './components/Login.vue'

export default {
  name: 'app',
  components: {
    Index,
    Login
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  color: #2c3e50;
  text-align: center;
  margin-top: 60px;
}
</style>
