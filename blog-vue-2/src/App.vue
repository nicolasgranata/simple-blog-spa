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
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@700;900&display=swap');

#app {
  font-family: 'Open Sans',sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  -webkit-text-size-adjust: 100%;
  box-sizing: border-box;
  color: #2c3e50;
}

body.dark-mode {
  background-color: #282c35;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
}

nav a.router-link-exact-active {
  color: lightslategray;
}

a {
  background-color: transparent;
}
</style>
