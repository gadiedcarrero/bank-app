<template>
  <div class="navbar">
    <div class="navbar__container">
      <div class="navbar__logo-container">
        <img src="/logo.svg" alt="logo" />
      </div>

      <HorizontalMenu v-if="!isMobile" />

      <ButtonClassic buttonText="Request Invite" v-if="!isMobile" />

      <HamburgerButton v-if="isMobile" @toggle="toggleMenu" />
    </div>
  </div>
  <transition name="fade">
    <div class="backdrop" v-if="showMenu"></div>
  </transition>
  <VerticalMenu
    class="navbar__vertical-menu"
    :class="{ open: showMenu, closed: !showMenu }"
    v-if="isMobile"
  />
</template>

<script setup>
import { ref, onMounted, onUnmounted, watch } from 'vue'

import HamburgerButton from './ButtonHamburgerComponent.vue'
import VerticalMenu from './VerticalNavComponent.vue'
import HorizontalMenu from './HorizontalNavComponent.vue'
import ButtonClassic from './ButtonClassicComponent.vue'

let showMenu = ref(false)
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

watch(showMenu, (newValue) => {
  if (newValue) {
    const scrollbarWidth = window.innerWidth - document.documentElement.clientWidth
    document.body.style.paddingRight = `${scrollbarWidth}px`
    document.body.style.overflow = 'hidden'
  } else {
    document.body.style.paddingRight = ''
    document.body.style.overflow = ''
  }
})

const toggleMenu = (event) => {
  event.stopPropagation()
  showMenu.value = !showMenu.value
}
</script>

<style lang="scss" scoped>
@import '@/assets/variables.scss';

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease-in-out;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}

.fade-enter-to,
.fade-leave {
  opacity: 1;
}

.backdrop {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(to bottom, rgba(0, 0, 0, 0.9), rgba(128, 128, 128, 0.5));
  z-index: 99;
}
.navbar {
  position: relative;
  background-color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 60px;
  z-index: 200;

  @media (min-width: $breakpoint) {
    height: 80px;
  }

  &__logo-container {
    padding: 8px;
  }

  &__container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    color: hsl(233, 8%, 62%);
    width: 100%;
    @include responsive-width;
  }

  &__vertical-menu.open {
    animation: slideDown $animation-duration ease-out forwards;
  }

  &__vertical-menu.closed {
    animation: slideUp $animation-duration ease-out forwards;
  }
}
</style>
