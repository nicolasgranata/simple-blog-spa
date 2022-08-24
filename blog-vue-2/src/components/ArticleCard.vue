<template>
    <article class="article-card">
      <h3>
        <router-link
          class="article-link"
          :to="{ name: 'article-detail', params: { id: '1' } }"
        >{{ title }}</router-link>
      </h3>
      <p>{{ body }}</p>
      <small class="article-posted-by">{{ getPostedBy()}}</small>
    </article>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component
export default class ArticleCard extends Vue {
  @Prop({ default: '' }) public title!: string;
  @Prop({ default: '' }) public body!: string;
  @Prop({ default: '' }) public date!: string;
  @Prop({ default: '' }) public author!: string;

  public getPostedBy(): string {
    return `Posted by ${this.author} on ${this.date}`
  }
}
</script>

<style scoped>
.article-card {
  padding: 1rem;
}

.article-link {
  color: var(--primary-color);
  text-decoration: none;
  font-weight: 900;
  font-family: Montserrat, 'Open Sans', sans-serif;
  font-size: 1.75rem;
}

.dark-mode .article-link {
  color: var(--primary-color-dark-mode);
}

.article-posted-by {
  font-style: oblique;
}

.dark-mode .article-posted-by {
  color: var(--secondary-color-dark-mode);
}

.dark-mode p {
  color: var(--primary-color-dark-mode);
}
</style>
