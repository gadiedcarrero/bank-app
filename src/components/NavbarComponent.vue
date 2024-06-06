<template>
  <div class="navbar">
    <div class="navbar__container">
      <img src="/logo.svg" alt="logo" />

      <HorizontalMenu v-if="!isMobile" />

      <ButtonClassic buttonText="Request Invite" v-if="!isMobile" />

      <HamburgerButton v-if="isMobile" @toggle="toggleMenu" />
    </div>
  </div>
  <VerticalMenu v-if="showMenu && isMobile" />
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

import HamburgerButton from './ButtonHamburgerComponent.vue'
import VerticalMenu from './VerticalNavComponent.vue'
import HorizontalMenu from './HorizontalNavComponent.vue'
import ButtonClassic from './ButtonClassicComponent.vue'

let isMobile = ref(
  window.innerWidth <
    parseInt(getComputedStyle(document.documentElement).getPropertyValue('--breakpoint'))
)

const updateIsMobile = () => {
  isMobile.value =
    window.innerWidth <
    parseInt(getComputedStyle(document.documentElement).getPropertyValue('--breakpoint'))
}

onMounted(() => {
  window.addEventListener('resize', updateIsMobile)
})

onUnmounted(() => {
  window.removeEventListener('resize', updateIsMobile)
})

let showMenu = ref(false)

const toggleMenu = (event) => {
  event.stopPropagation()
  showMenu.value = !showMenu.value
}
</script>

<style lang="scss" scoped>
@import '@/assets/variables.scss';

.navbar {
  background-color: white;
  height: 80px;
  display: flex;
  align-items: center;
  justify-content: center;

  &__container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    color: hsl(233, 8%, 62%);
    width: $width-desktop;
  }
}
</style>
