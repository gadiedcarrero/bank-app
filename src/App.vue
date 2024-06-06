<script setup>
import NavbarComponent from './components/NavbarComponent.vue'
import AboutPage from './pages/AboutPage.vue'
import ArticlesPage from './pages/ArticlesPage.vue'
import HomePage from './pages/HomePage.vue'
</script>

<template>
  <div>
    <NavbarComponent />
    <HomePage />
    <AboutPage />
    <ArticlesPage />
  </div>
</template>

<style scoped>
@media (min-width: 1024px) {
}
</style>
