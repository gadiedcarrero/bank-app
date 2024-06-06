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
  height: 700px;
  display: flex;
  align-items: center;
  justify-content: center;

  &__container {
    width: $width-desktop;
  }

  &__title {
    font-size: $font-size-about-title;
    font-weight: $font-weight-light;
    color: $dark-blue;
    margin-bottom: 32px;
  }

  &__text {
    font-size: $font-size-normal;
    color: $grayish-blue;
    width: 650px;
    margin-bottom: 74px;
  }

  &__card-group {
    display: flex;
    justify-content: space-between;
    gap: 24px;
  }
}
</style>
