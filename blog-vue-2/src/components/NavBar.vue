<template>
    <div>
        <nav>
        <router-link :to="{ name: 'home' }">Home</router-link> |
        <router-link :to="{ name: 'article-create' }">Create Article</router-link>
        <button v-on:click="changeTheme()"/>
        </nav>
    </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

@Component
export default class NavBar extends Vue {
  public changeTheme(): void {
    document.body.classList.toggle('dark-mode')
  }
}
</script>
