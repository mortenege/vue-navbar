<template>
  <div id="app">
    <navbar></navbar>
    <h2>{{ msg }}</h2>
  </div>
</template>

<script>
import Navbar from './Navbar.vue'

export default {
  name: 'app',
  components: {
    navbar: Navbar
  },
  data () {
    return {
      msg: 'Welcome to the Navbar Example'
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}
</style>
