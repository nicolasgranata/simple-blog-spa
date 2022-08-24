<template>
<div>
    <div class="header">
        <h1 class="title">Blog example using Vue2</h1>
        <h2 class="sub-title">A blog example using Vue2</h2>
    </div>
    <div class="container">
           <ArticleCard class="item" v-for="article in this.articles" :key="article.id"
            :article="article"
          />
    </div>
</div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import ArticleCard from '@/components/ArticleCard.vue'
import Article from '../models'

@Component({
  components: {
    ArticleCard
  }
})
export default class HomeView extends Vue {
  public articles: Article[] = [];

  created() {
    this.articles.push({
      id: 1,
      author: 'John Doe',
      body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis vehicula et sem et lobortis. Phasellus consequat convallis auctor. Nulla turpis turpis, faucibus ut mi et, dictum efficitur arcu. Integer venenatis interdum tincidunt.',
      title: 'Nunc non congue libero. Curabitur.',
      date: 'August 22, 2022'
    })
    this.articles.push({
      id: 2,
      author: 'Jane Doe',
      body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis vehicula et sem et lobortis. Phasellus consequat convallis auctor. Nulla turpis turpis, faucibus ut mi et, dictum efficitur arcu. Integer venenatis interdum tincidunt.',
      title: 'Aenean non pretium nisl.',
      date: 'August 22, 2022'
    })
    this.articles.push({
      id: 3,
      author: 'John Doe',
      body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis vehicula et sem et lobortis. Phasellus consequat convallis auctor. Nulla turpis turpis, faucibus ut mi et, dictum efficitur arcu. Integer venenatis interdum tincidunt.',
      title: 'Nunc non congue libero. Curabitur.',
      date: 'August 22, 2022'
    })
    this.articles.push({
      id: 4,
      author: 'Jane Doe',
      body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis vehicula et sem et lobortis. Phasellus consequat convallis auctor. Nulla turpis turpis, faucibus ut mi et, dictum efficitur arcu. Integer venenatis interdum tincidunt.',
      title: 'Aenean non pretium nisl.',
      date: 'August 22, 2022'
    })
    this.articles.push({
      id: 5,
      author: 'John Doe',
      body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis vehicula et sem et lobortis. Phasellus consequat convallis auctor. Nulla turpis turpis, faucibus ut mi et, dictum efficitur arcu. Integer venenatis interdum tincidunt.',
      title: 'Nunc non congue libero. Curabitur.',
      date: 'August 22, 2022'
    })
    this.articles.push({
      id: 6,
      author: 'Jane Doe',
      body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis vehicula et sem et lobortis. Phasellus consequat convallis auctor. Nulla turpis turpis, faucibus ut mi et, dictum efficitur arcu. Integer venenatis interdum tincidunt.',
      title: 'Aenean non pretium nisl.',
      date: 'August 22, 2022'
    })
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

.sub-title {
  color: var(--primary-color);
  font-weight: 700;
  font-family: Montserrat, 'Open Sans', sans-serif;
  font-size: 1.5rem;
  margin-top: 0;
}

.container {
  padding: 1em;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: left;
}

.item {
  max-width: 40%;
}

@media (max-width: 1000px) {
  .item {
    max-width: 80%;
  }
}

.dark-mode .container {
  background-color: var(--main-bg-color-dark-mode);
}

.dark-mode .title {
  color: var(--primary-color-dark-mode);
}

.dark-mode .sub-title {
  color: var(--primary-color-dark-mode);
}
</style>
