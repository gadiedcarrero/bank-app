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
  width: 100%;
  padding-top: 32px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding-bottom: 70px;

  &__title {
    font-size: $font-size-about-title;
    font-weight: $font-weight-light;
    color: $dark-blue;
    padding-top: 96px;
    color: $dark-blue;
    padding-bottom: 56px;
  }

  &__container {
    width: $width-desktop;
  }

  &__card-group {
    display: flex;
    justify-content: space-between;
    gap: 24px;
  }

  &__text {
    font-size: $font-size-normal;
    color: $grayish-blue;
    width: 650px;
    margin-bottom: 74px;
  }
}
</style>
