<script setup lang="ts">
</script>

<template>
  <div :class="$style.sideBarWrapper">
    <div :class="$style.sideBarHeader">
      <SideBarAddBtn />
    </div>

    <div :class="$style.sideBarBody">
      <SideBarCategory />

      <div :class="$style.sideBarBodyStorage">
        <div :class="$style.sideBarBodyStorageBar">
          <div :class="$style.sideBarBodyStorageProgress" />
        </div>

        <span :class="$style.sideBarBodyStorageTitle">Đã sử dụng 4.5GB trong tổng số 15GB</span>

        <button :class="$style.sideBarBodyStorageBtn">
          Mua thêm bộ nhớ
        </button>
      </div>
    </div>
  </div>
</template>

<style lang='scss' module>
  .sideBarWrapper {
    flex: 0 0 250px;
    height: 90vh;
    max-width: 250px;
  }

  .sideBarHeader {
    padding: 8px 16px 16px 0;
  }

  .sideBarBody {
    padding: 8px 0 16px;
  }

  .sideBarBodyStorage {
    display: flex;
    flex-direction: column;
    gap: 10px;
    padding: 8px 0 8px 0;
    margin-left: 16px;
    max-width: 175px;
  }

  .sideBarBodyStorageBar {
    background-color: #e9eef6;
    width: 100%;
    line-height:20px;
    height: 5px;
    border-radius: 100px;
  }

  .sideBarBodyStorageProgress {
    background-color: var(--color-primary);
    width: 30%;
    line-height:20px;
    height: 5px;
    border-radius: 100px;
  }

  .sideBarBodyStorageTitle {
    line-height: 20px;
    font-family: 'Open Sans', sans-serif;
    font-size: 14px;
    margin-bottom: 8px;
  }

  .sideBarBodyStorageBtn {
    border: 1px solid black;
    color: var(--color-primary);
    border-radius: 99999px;
    line-height: 20px;
    font-weight: 500;
    width: 165px;
    height: 36px;

    &:hover {
      background-color: var(--color-hover);
    }

    &:active {
      background-color: #E6EDFA;
    }
  }
</style>
