<template>
  <div class="articles">
    <div class="articles__container">
      <div class="articles__title">Latest Articles</div>
      <div class="articles__card-group">
        <CardComponentArticle
          v-for="(article, index) in cardArticle"
          :key="index"
          :img="article.img"
          :author="article.author"
          :title="article.title"
          :text="article.text"
        />
      </div>
    </div>
  </div>
</template>

<script setup>
import CardComponentArticle from '@/components/CardComponentArticle.vue'
import cardArticle from '@/utils/cardArticles.js'
</script>

<style lang="scss" scoped>
@import '@/assets/variables.scss';

.articles {
  background-color: $very-light-gray;
  padding-top: 96px;
  padding-bottom: 70px;

  &__title {
    font-size: $font-size-about-title;
    font-weight: $font-weight-light;
    color: $dark-blue;
    padding-bottom: 56px;
  }

  &__container {
    @include responsive-width;
  }

  &__card-group {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    gap: 24px;
    @media (min-width: $breakpoint-sd) {
      flex-direction: row;
    }
  }

  &__text {
    font-size: $font-size-normal;
    color: $grayish-blue;
    margin-bottom: 74px;
  }
}
</style>
