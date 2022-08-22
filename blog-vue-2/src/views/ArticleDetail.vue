<template>
    <div>
        <h1>Showing Artcile #{{ id }}</h1>
    </div>
</template>

<script lang="ts">
import ArticleCard from '@/components/ArticleCard.vue'
import { Component, Vue, Prop } from 'vue-property-decorator'

@Component({
  components: {
    ArticleCard
  }
})
export default class ArticleDetail extends Vue {
    @Prop({ default: null }) public id!: number | null
}
</script>
