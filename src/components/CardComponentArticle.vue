<template>
  <div class="card-article" tabindex="0">
    <img class="card-article__img" :src="img" alt="image Article" />
    <div class="card-article__container">
      <div class="card-article__author">By {{ author }}</div>
      <div class="card-article__title">
        {{ title }}
      </div>
      <div class="card-article__text">
        {{ text }}
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue'

defineProps({
  img: {
    type: String,
    default: ''
  },
  author: {
    type: String,
    default: ''
  },
  title: {
    type: String,
    default: ''
  },
  text: {
    type: String,
    default: ''
  }
})
</script>

<style lang="scss" scoped>
@import '@/assets/variables.scss';

.card-article {
  display: flex;
  flex-direction: column;
  width: 100%;
  background-color: $white;
  cursor: pointer;
  overflow: hidden;

  &:hover,
  &:focus,
  &:active {
    .card-article__title {
      color: $lime-green;
    }
  }

  &__container {
    border-radius: 0 0 8px 8px;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: center;
    width: 100%;
    padding: 26px;
    background: $white;
  }

  &__img {
    border-radius: 8px 8px 0 0;
    width: 100%;
    height: 200px;
    object-fit: cover;
    transition: transform 0.3s ease-in-out;
  }

  &__author {
    font-size: $font-size-card-author;
    color: $grayish-blue;
    margin-bottom: 16px;
  }

  &__title {
    font-size: $font-size-card-title;
    color: $dark-blue;
    margin-bottom: 16px;
  }

  &__text {
    font-size: $font-size-card-article-text;
    color: $grayish-blue;
    display: -webkit-box;
    -webkit-line-clamp: 4;
    -webkit-box-orient: vertical;
    overflow: hidden;
    text-overflow: ellipsis;
  }
}
</style>
