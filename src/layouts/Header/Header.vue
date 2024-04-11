<script setup>
import logo from '@/assets/images/google-drive-logo.png'
</script>

<template>
  <div :class="$style.headerWrapper">
    <div :class="$style.headerLogo">
      <img :src="logo" alt="Google Drive Logo">
    </div>
  </div>
</template>

<style module>
.headerWrapper {
  display: flex;
  justify-content: space-around;
  align-items: center;
}
</style>
