<template>
  <div class="about">
    <div class="about__container">
      <div class="about__title">Why choose Easybank?</div>
      <p class="about__text">
        We leverage Open Banking to turn your bank account into your financial hub. Control your
        finances like never before.
      </p>
      <div class="about__card-group">
        <CardComponentAbout
          v-for="(card, index) in cardAbout"
          :key="index"
          :icon="card.icon"
          :title="card.title"
          :description="card.description"
        />
      </div>
    </div>
  </div>
</template>

<script setup>
import CardComponentAbout from '@/components/CardComponentAbout.vue'
import cardAbout from '@/utils/cardAbout.js'
</script>

<style lang="scss" scoped>
@import '@/assets/variables.scss';
.about {
  background-color: $light-grayish-blue;
  width: 100%;

  &__container {
    @include responsive-width;
  }

  &__title {
    font-size: $font-size-about-title;
    font-weight: $font-weight-light;
    color: $dark-blue;
    margin-bottom: 32px;
    text-align: center;
    padding-top: 64px;

    @media (min-width: $breakpoint) {
      text-align: left;
    }
  }

  &__text {
    font-size: $font-size-normal;
    color: $grayish-blue;
    margin-bottom: 74px;
    text-align: center;

    @media (min-width: $breakpoint) {
      text-align: left;
      width: 650px;
    }
  }

  &__card-group {
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 24px;
    padding-bottom: 64px;

    @media (min-width: $breakpoint) {
      flex-direction: row;
      justify-content: space-between;
    }
  }
}
</style>
