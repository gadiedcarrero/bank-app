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
  position: absolute;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: $white;
  border-radius: 8px;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  width: 90%;
  z-index: 100;
  padding: 24px;
  left: 0;
  right: 0;
  top: 50px;
  margin: auto;
}

.nav-list {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  list-style: none;
  gap: 36px;
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
    bottom: -8px;
    left: 0;
    width: 100%;
    height: 3px;
    background: linear-gradient(to right, $lime-green, $bright-cyan);
  }
}
</style>
