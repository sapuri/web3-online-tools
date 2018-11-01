<template>
  <div id="app">
    <Home/>
  </div>
</template>

<script>
  import Home from './components/Home.vue'

  export default {
    name: 'app',
    components: {
      Home
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

  h3 {
    margin: 40px 0 0;
  }

  a {
    color: #2980B9;
    text-decoration: none;
  }
</style>
