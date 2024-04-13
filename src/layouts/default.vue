<script setup lang="ts">
import NavBar from '@/components/NavBar/NavBar.vue'
import Header from '@/layouts/Header/Header.vue'
</script>

<template>
  <div :class="$style.layoutWrapper">
    <header>
      <Header />
    </header>

    <div :class="$style.layoutContent">
      <NavBar />

      <RouterView />
    </div>
  </div>
</template>

<style module>
.layoutWrapper {
  padding: 8px 20px;
  height: 100%;
  background-color: #F8FAFD;
}

.layoutContent {
  display: flex;
  justify-content: flex-start;
}

.layoutContentRoute {
    background-color: #ffffff;
    border-radius: 30px;
    padding: 30px;
    flex: 1 1 auto;
}
</style>
