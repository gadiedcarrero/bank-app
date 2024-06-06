<template>
  <nav class="nav">
    <ul class="nav-list">
      <li class="nav-item" v-for="(item, index) in navItems" :key="index">
        <a :class="{ 'nav-link-active': activeItem === item }" @click="activeItem = item">{{
          item
        }}</a>
      </li>
    </ul>
  </nav>
</template>

<script setup>
import { ref } from 'vue'
import { navItems } from '../utils/navItems'

const activeItem = ref(navItems[0])
</script>

<style lang="scss" scoped>
@import '@/assets/variables.scss';

.nav {
  display: flex;
  justify-content: space-between;
}

.nav-list {
  display: flex;
  list-style: none;
  gap: 48px;
}
.nav-item {
  cursor: pointer;

  &:hover {
    color: $dark-blue;
  }
}

.nav-link-active {
  position: relative;
  color: $dark-blue;

  &::after {
    content: '';
    position: absolute;
    bottom: -28px;
    left: 0;
    width: 100%;
    height: 3px;
    background: linear-gradient(to right, $lime-green, $bright-cyan);
  }
}
</style>
