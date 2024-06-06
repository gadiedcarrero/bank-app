<template>
  <div class="home">
    <div class="home__container">
      <div class="home__left">
        <div class="home__title">Next generation digital banking</div>
        <div class="home__text">
          Take your financial life online. Your Easybank account will be a one-stop-shop for
          spending, saving, budgeting, investing, and much more.
        </div>
        <ButtonClassic buttonText="Request Invite" />
      </div>
    </div>
    <div class="home__right-bg">
      <img class="home__img-bg" src="/bg-intro-desktop.svg" alt="bg intro desktop" />
    </div>
    <div class="home__right-mockups">
      <img class="home__img-mockups" src="/image-mockups.png" alt="image mockups" />
    </div>
  </div>
</template>

<script setup>
import ButtonClassic from '@/components/ButtonClassicComponent.vue'
</script>

<style lang="scss" scoped>
@import '@/assets/variables.scss';
.home {
  background-color: $very-light-gray;
  height: 656px;
  width: 100%;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;

  &__container {
    width: $width-desktop;
  }

  &__left {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    width: 450px;
    gap: 24px;
  }

  &__title {
    font-size: $font-size-heading;
    font-weight: $font-weight-light;
    color: dark-blue;
  }

  &__text {
    font-size: $font-size-normal;
    color: $grayish-blue;
  }

  &__right-bg {
    position: absolute;
    overflow: hidden;
    height: 656px;
    width: 100%;
  }

  &__img-bg {
    position: absolute;
    top: -265px;
    right: -469px;
  }

  &__right-mockups {
    position: absolute;
    overflow: hidden;
    top: 0;
    right: 0;
    width: 100%;
    height: 805px;
  }

  &__img-mockups {
    position: absolute;
    top: -123px;
    right: -131px;
  }
}
</style>
