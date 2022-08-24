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
@import url('assets/colors.css');

#app {
  font-family: 'Open Sans',sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  -webkit-text-size-adjust: 100%;
  box-sizing: border-box;
  color: var( --secondary-color);
}

.dark-mode #app {
  color: var(--secondary-color-dark-mode);
}

body {
  background-color: var(--main-bg-color);
}

body.dark-mode {
  background-color: var(--main-bg-color-dark-mode);
}

nav a {
  font-weight: bold;
  color: var(--secondary-color);
  text-decoration: none;
}

.dark-mode nav a {
  color: var(--link-text-color-dark-mode);
}

nav a.router-link-exact-active {
  color: var(--active-link-color);
}

.dark-mode nav a.router-link-exact-active  {
  color: var(--active-link-color-dark-mode);
}

a {
  background-color: transparent;
}
</style>
