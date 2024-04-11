<script setup lang="ts">
import NavBar from '@/components/NavBar/NavBar.vue'
import Header from '@/layouts/Header/Header.vue'
</script>

<template>
  <header>
    <Header />
  </header>

  <div :class="$style.layoutContent">
    <NavBar />
    <RouterView />
  </div>
</template>

<style module>
.layoutContent {
  display: flex;
  justify-content: flex-start;
  align-items: center;
}
</style>
