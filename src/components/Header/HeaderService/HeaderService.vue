<script setup>
import { GOOGLE_ICON_API } from '@/constant'
</script>

<template>
  <div :class="$style.serviceWrapper">
    <div :class="[$style.serviceWrapperGroup, $style.serviceWrapperList]">
      <div v-for="(item, index) in GOOGLE_ICON_API" :key="index" :class="$style.serviceWrapperItem">
        <a href="/">
          <!-- <img :src="item.image" alt="gg services"> -->
          <el-avatar :size="53" :src="circleUrl" />
        </a>

        <p>{{ item.name }}</p>
      </div>
    </div>

    <div :class="[$style.serviceWrapperGroup, $style.serviceWrapperList]">
      <div v-for="(item, index) in GOOGLE_ICON_API" :key="index" :class="$style.serviceWrapperItem">
        <a href="/">
          <!-- <img :src="item.image" alt="gg services"> -->
          <el-avatar :size="53" :src="circleUrl" />
        </a>

        <p>{{ item.name }}</p>
      </div>
    </div>
  </div>
</template>

<style lang="scss" module>
    .serviceWrapper {
        width: 370px;
        height: 470px;
        padding: 10px;
        background-color: var(--color-gray-lighter);
        border-radius: 30px;
        overflow-y: auto;
    }

    .serviceWrapperGroup {
        width: 100%;
        padding: 24px 20px;
        background-color: #ffffff;
        
        &:first-child {
            border-top-left-radius: 20px;
            border-top-right-radius: 20px;
            border-bottom-left-radius: 5px;
            border-bottom-right-radius: 5px;
            margin-bottom: 5px;
        }

        &:last-child {
            border-top-left-radius: 5px;
            border-top-right-radius: 5px;
            border-bottom-left-radius: 20px;
            border-bottom-right-radius: 20px;
        }
    }

    .serviceWrapperList {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-template-rows: repeat(6,96px);
        font-family: 'Roboto', sans-serif;
    }

    .serviceWrapperItem {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width: 96px;
        height: 96px;
        border-radius: 20px;

        &:hover {
            background-color:#e9eef6;
        }
    }

    :global(.el-dropdown__popper.el-popper) {
        border-radius: 30px;
    }
</style>
