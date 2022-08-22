<template>
  <router-link :to="{ name: 'article-detail', params: { id: '1'} }">
      <div>
          <h3>{{title}}</h3>
          <h4>{{author}}</h4>
      </div>
  </router-link>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component
export default class ArticleCard extends Vue {
  @Prop({ default: '' }) public title!: string;
  @Prop({ default: '' }) public author!: string;
}
</script>

<style scoped>

</style>
