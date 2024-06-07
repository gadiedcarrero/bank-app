<template>
  <div class="home">
    <div class="home__bg-movile" v-if="isMobile">
      <div class="home__bg-movile-container">
        <img class="home__img-mockups-movil" src="/image-mockups.png" alt="image mockups" />
      </div>
    </div>
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
    <div class="home__right-bg" v-if="!isMobile">
      <img class="home__img-bg" src="/bg-intro-desktop.svg" alt="bg intro desktop" />
    </div>
    <div class="home__right-mockups">
      <img class="home__img-mockups" src="/image-mockups.png" alt="image mockups" />
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import ButtonClassic from '@/components/ButtonClassicComponent.vue'

let isMobile = ref(window.innerWidth < 986)

const updateIsMobile = () => {
  isMobile.value = window.innerWidth < 986
}

onMounted(() => {
  window.addEventListener('resize', updateIsMobile)
})

onUnmounted(() => {
  window.removeEventListener('resize', updateIsMobile)
})
</script>

<style lang="scss" scoped>
@import '@/assets/variables.scss';
.home {
  background-color: $very-light-gray;
  width: 100%;
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding-bottom: 100px;

  @media (min-width: $breakpoint-sd) {
    flex-direction: row;
    justify-content: flex-start;
    height: 658px;
  }

  &__bg-movile {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background-image: url('/bg-intro-mobile.svg');
    background-size: cover;
    background-position: center;
  }

  &__bg-movile-container {
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  &__img-mockups-movil {
    margin-left: 5%;
    margin-right: 5%;
    width: 80%;
    height: auto;
    margin-top: -29%;
  }

  &__container {
    @include responsive-width;
    margin-top: 48px;
  }

  &__left {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100%;
    gap: 24px;

    @media (min-width: $breakpoint-sd) {
      align-items: flex-start;
      width: 450px;
      gap: 24px;
    }
  }

  &__title {
    font-size: $font-size-heading;
    font-weight: $font-weight-light;
    color: $dark-blue;
    text-align: center;

    @media (min-width: $breakpoint-sd) {
      text-align: left;
    }
  }

  &__text {
    font-size: $font-size-normal;
    color: $grayish-blue;
    text-align: center;

    @media (min-width: $breakpoint-sd) {
      text-align: left;
    }
  }

  &__right-bg {
    display: none;
    position: absolute;
    overflow: hidden;
    height: 658px;

    width: 100%;
    top: 0;
    @media (min-width: $breakpoint-sd) {
      display: block;
    }
  }

  &__img-bg {
    position: absolute;
    top: -265px;
    right: -469px;
    display: none;
    @media (min-width: $breakpoint-sd) {
      display: block;
    }
    @media (min-width: $breakpoint-sd) and (max-width: $breakpoint-md) {
      right: calc(50vw - 1229px);
    }
  }

  &__right-mockups {
    position: absolute;
    overflow: hidden;
    top: 0;
    right: 0;
    width: 100%;
    height: 805px;
    display: none;
    @media (min-width: $breakpoint-sd) {
      display: block;
    }
  }

  &__img-mockups {
    position: absolute;
    top: -123px;
    right: -131px;
    display: none;
    @media (min-width: $breakpoint-sd) {
      display: block;
    }
    @media (min-width: $breakpoint-sd) and (max-width: $breakpoint-md) {
      right: calc(50vw - 880px);
    }
  }
}
</style>
