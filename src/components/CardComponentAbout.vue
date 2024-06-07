<template>
  <div class="card-about">
    <img class="card-about__icon" :src="icon" alt="image icon" />
    <div class="card-about__title">
      {{ title }}
    </div>
    <div class="card-about__description">
      {{ description }}
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue'

defineProps({
  icon: {
    type: String,
    default: ''
  },
  title: {
    type: String,
    default: ''
  },
  description: {
    type: String,
    default: ''
  }
})
</script>

<style lang="scss" scoped>
@import '@/assets/variables.scss';

.card-about {
  border-radius: 8px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100%;
  @media (min-width: $breakpoint) {
    align-items: flex-start;
  }

  &__title {
    margin-top: 42px;
    font-size: $font-size-card-title;
    color: $dark-blue;
    margin-bottom: 32px;
    text-align: center;
  }

  &__description {
    font-size: $font-size-normal;
    color: $grayish-blue;
    text-align: center;

    @media (min-width: $breakpoint) {
      text-align: left;
    }
  }
}
</style>
