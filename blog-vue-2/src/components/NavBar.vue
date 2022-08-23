<template>
    <div class="nav-div">
        <nav class="nav-content">
          <router-link :to="{ name: 'home' }">Home</router-link> |
          <router-link :to="{ name: 'article-create' }">Create Article</router-link>
        </nav>
        <ThemeSwitch class="item-theme" />
    </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import ThemeSwitch from '@/components/ThemeSwitch.vue'

@Component({
  components: {
    ThemeSwitch
  }
})
export default class NavBar extends Vue {}
</script>

<style scoped>
.nav-div {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
}

.nav-content {
  grid-column:2;
  text-align: center;
}

.item-theme {
  grid-column: 3;
  justify-self: flex-end;
}

@media (max-width: 1000px) {
  .nav-content {
    grid-column:1;
    width: max-content;
  }
}
</style>
