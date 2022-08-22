<template>
    <div>
        <h1>Blog example using Vue2</h1>
        <h2>A blog example using Vue2</h2>
        <div class="container">
           <ArticleCard class="item" v-for="article in this.articles" :key="article.id"
            :author="article.author"
            :body="article.body"
            :title="article.title"
            :date="article.date"
          />
        </div>
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
  public articles: any[] = [];

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
.container {
  padding: 1em;
  display: flex;
  flex-direction: column;
  align-items: center;
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
    background-color: #282c35;
  }

.dark-mode h1, h2 {
  color: lightslategray
}
</style>
