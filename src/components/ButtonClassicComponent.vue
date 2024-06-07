<template>
  <button class="btn-classic">{{ buttonText }}</button>
</template>

<script setup>
import { defineProps } from 'vue'

defineProps({
  buttonText: {
    type: String,
    default: 'Request Invite'
  }
})
</script>

<style lang="scss" scoped>
@import '@/assets/variables.scss';

.btn-classic {
  color: white;
  border-radius: 50px;
  background: linear-gradient(to right, $lime-green, $bright-cyan);
  padding: 16px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: $font-size-btn;
  cursor: pointer;
  border: none;
  white-space: nowrap;
  font-weight: $font-weight-bold;
  transition: box-shadow 0.3s ease;

  &:hover {
    box-shadow: inset 0 0 0 1000px rgba(255, 255, 255, 0.4);
  }
}
</style>
