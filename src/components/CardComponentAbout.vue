<template>
  <div class="card-about">
    <div class="card-about__icon-container">
      <img class="card-about__icon" :src="icon" alt="image icon" />
    </div>
    <div class="card-about__title">
      {{ title }}
    </div>
    <div class="card-about__text">
      {{ text }}
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue'

defineProps({
  icon: {
    type: String,
    default: 'icon'
  },
  title: {
    type: String,
    default: 'Request Invite'
  },
  text: {
    type: String,
    default: 'Request Invite'
  }
})
</script>

<style lang="scss" scoped></style>
