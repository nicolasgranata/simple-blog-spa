<template>
    <div>
        <h1>Articles Listing</h1>
        <ArticleCard :author="author" :title="title"></ArticleCard>
    </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import ArticleCard from '@/components/ArticleCard.vue'

@Component({
  components: {
    ArticleCard
  }
})
export default class HomeView extends Vue {
  public title = 'Title';
  public author = 'Author';
}
</script>
