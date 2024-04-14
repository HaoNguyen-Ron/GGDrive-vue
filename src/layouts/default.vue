<script setup lang="ts">
import SideBar from '@/components/NavBar/SideBar.vue';
import Header from '@/layouts/Header/Header.vue';
</script>

<template>
  <div :class="$style.layoutWrapper">
    <header>
      <Header />
    </header>

    <div :class="$style.layoutBody">
      <SideBar />

      <div :class="$style.layoutContent">
        <RouterView />
      </div>
    </div>
  </div>
</template>

<style module>
.layoutWrapper {
  height: 100%;
  background-color: #F8FAFD;
  padding: 0 16px;
}

.layoutBody {
  display: flex;
  justify-content: flex-start;
}

.layoutContentRoute {
    background-color: #ffffff;
    border-radius: 30px;
    padding: 30px;
    flex: 1 1 auto;
}

.layoutContent {
  
}
</style>
