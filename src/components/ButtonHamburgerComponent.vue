<template>
  <label class="hamburger-button" @click="toggleMenu">
    <input type="checkbox" @click.stop />
  </label>
</template>

<script setup>
import { defineEmits } from 'vue'

const emit = defineEmits(['toggle'])

const toggleMenu = (event) => {
  event.stopPropagation()
  emit('toggle', event)
}
</script>

<style lang="scss" scoped>
@import '@/assets/variables.scss';

.hamburger-button {
  display: inline-flex;
  flex-direction: column;
  gap: $hamburger-gap;
  cursor: pointer;
  z-index: 20;
  padding: 8px;
}

.hamburger-button::before,
.hamburger-button::after,
.hamburger-button input {
  content: '';
  width: $bar-width;
  height: $bar-height;
  background-color: $foreground;
  border-radius: $hamburger-border-radius;
  transform-origin: left center;
  transition:
    opacity $animation-duration,
    width $animation-duration,
    rotate $animation-duration,
    translate $animation-duration;
}

.hamburger-button input {
  appearance: none;
  padding: 0;
  margin: 0;
  outline: none;
  pointer-events: none;
}

.hamburger-button:has(input:checked)::before {
  rotate: 45deg;
  width: $hamburger-x-width;
  translate: 0 calc(-1 * $hamburger-x-height);
}

.hamburger-button:has(input:checked)::after {
  rotate: -45deg;
  width: $hamburger-x-width;
  translate: 0 $hamburger-x-height;
}

.hamburger-button input:checked {
  opacity: 0;
  width: 0;
}
</style>
