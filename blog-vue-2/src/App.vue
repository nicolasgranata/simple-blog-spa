<template>
  <div id="app">
    <NavBar />
    <router-view/>
  </div>
</template>

<script lang='ts'>
import NavBar from '@/components/NavBar.vue'

export default {
  components: {
    NavBar
  }
}
</script>

<style>
#app {
  font-family: 'Open Sans',sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  -webkit-text-size-adjust: 100%;
  text-align: center;
  color: #2c3e50;
}

body.dark-mode {
  background-color: #282c35;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: lightslategray;
}

a {
  background-color: transparent;
}
</style>
