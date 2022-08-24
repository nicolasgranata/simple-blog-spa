<template>
      <main>
          <article>
            <header class="header">
              <h1 class="title">{{ article?.title }}</h1>
              <small class="article-posted-by">{{ getPostedBy() }}</small>
            </header>
            <div class="container-article">
              <p>{{ article?.body }}</p>
            </div>
          </article>
      </main>
</template>

<script lang="ts">
import ArticleCard from '@/components/ArticleCard.vue'
import Article from '@/models'
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component({
  components: {
    ArticleCard
  }
})
export default class ArticleDetail extends Vue {
  @Prop({ default: null }) public article!: Article;

  public getPostedBy(): string {
    return `Posted by ${this.article?.author} on ${this.article?.date}`;
  }
}
</script>

<style scoped>
.header {
  text-align: center;
}

.title {
  color: var(--primary-color);
  font-weight: 900;
  font-family: Montserrat, 'Open Sans', sans-serif;
  margin-bottom: 0;
  font-size: 2.5rem;
}

.dark-mode .title {
  color: var(--primary-color-dark-mode);
}

.container-article {
  padding: 1em;
  display: flex;
  margin-left: auto;
  margin-right: auto;
  max-width: 50rem;
}

.article-posted-by {
  margin-top: 1rem;
  font-style: oblique;
}

.dark-mode .article-posted-by {
  color: var(--secondary-color-dark-mode);
}

.dark-mode p {
  color: var(--primary-color-dark-mode);
}
</style>
