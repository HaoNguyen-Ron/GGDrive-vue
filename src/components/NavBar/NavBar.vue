<script setup lang="ts">

</script>

<template>
  <div :class="$style.navBarWrapper">
    <div :class="$style.navBarHeader">
      <button :class="$style.navBarAddBtn">
        <i class="fa-solid fa-plus" :class="$style.navBarItemIcon" />
        Mới
      </button>
    </div>

    <div :class="$style.navBarBody">
      <div :class="$style.navBarList">
        <div :class="$style.navBarItemGroup">
          <button :class="[$style.navBarBtn, $style.navBarItem]">
            <div :class="$style.navBarItemIcon">
              <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
              <i class="fa-solid fa-home" />
            </div>

            <span :class="$style.navBarItemContent">Trang chủ</span>
          </button>

          <button :class="[$style.navBarBtn, $style.navBarItem]">
            <div :class="$style.navBarItemIcon">
              <i class="fa-solid fa-caret-right" />
              <i class="fa-regular fa-hard-drive" />
            </div>

            <span :class="$style.navBarItemContent">Drive của tôi</span>
          </button>

          <button :class="[$style.navBarBtn, $style.navBarItem]">
            <div :class="$style.navBarItemIcon">
              <i class="fa-solid fa-caret-right" />
              <i class="fa-solid fa-computer" />
            </div>

            <span :class="$style.navBarItemContent">Máy Tính</span>
          </button>
        </div>

        <div :class="$style.navBarItemGroup">
          <button :class="[$style.navBarBtn, $style.navBarItem]">
            <div :class="$style.navBarItemIcon">
              <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
              <i class="fa-regular fa-user" />
            </div>

            <span :class="$style.navBarItemContent">Được chia sẻ với tôi</span>
          </button>

          <button :class="[$style.navBarBtn, $style.navBarItem]">
            <div :class="$style.navBarItemIcon">
              <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
              <i class="fa-regular fa-clock" />
            </div>

            <span :class="$style.navBarItemContent">Gần đây</span>
          </button>

          <button :class="[$style.navBarBtn, $style.navBarItem]">
            <div :class="$style.navBarItemIcon">
              <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
              <i class="fa-regular fa-star" />
            </div>

            <span :class="$style.navBarItemContent">Có gắn dấu sao</span>
          </button>
        </div>

        <div :class="$style.navBarItemGroup">
          <button :class="[$style.navBarBtn, $style.navBarItem]">
            <div :class="$style.navBarItemIcon">
              <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
              <i class="fa-regular fa-circle-xmark" />
            </div>

            <span :class="$style.navBarItemContent">Nội dung rác</span>
          </button>

          <button :class="[$style.navBarBtn, $style.navBarItem]">
            <div :class="$style.navBarItemIcon">
              <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
              <i class="fa-regular fa-trash-can" />
            </div>

            <span :class="$style.navBarItemContent">Thùng rác</span>
          </button>

          <button :class="[$style.navBarBtn, $style.navBarItem]">
            <div :class="$style.navBarItemIcon">
              <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
              <i class="fa-solid fa-cloud" />
            </div>

            <span :class="$style.navBarItemContent">Bộ nhớ</span>
          </button>
        </div>
      </div>

      <div :class="$style.navBarBodyStorage">
        <div :class="$style.navBarBodyStorageBar">
          <div :class="$style.navBarBodyStorageProgress" />
        </div>

        <span :class="$style.navBarBodyStorageTitle">Đã sử dụng 4.5GB trong tổng số 15GB</span>

        <button :class="$style.navBarBodyStorageBtn">
          Mua thêm bộ nhớ
        </button>
      </div>
    </div>
  </div>
</template>

<style lang='scss' module>
  .navBarWrapper {
    flex: 0 0 250px;
    height: 100%;
  }

  .navBarHeader {
    padding: 8px 0 16px;
  }

  .navBarAddBtn {
    display: flex;
    align-items:center;
    justify-content: flex-start;
    gap: 12px;
    border-radius: 16px;
    box-shadow: #000000 0px 3px 1px -2px;
    padding: 18px 20px 18px 16px;
    background-color: #ffffff;
    font-family: 'Arial', sans-serif;
    text-align:center;
    font-weight: 500;
    line-height:20px;
    color: #1f1f1f;
    font-size: 14px;
    cursor: pointer;

    &:hover {
      background-color: #e9eef6;
    }
  }

  .navBarBtn {
    display: flex;
    align-items:center;
    justify-content: flex-start;
    gap: 20px;
    font-family: 'Arial', sans-serif;
    text-align:center;
    font-weight: 500;
    line-height:20px;
    color: #1f1f1f;
    font-size: 14px;
    background-color: transparent;
    cursor: pointer;
  }

  .navBarBody {
    padding: 8px 0 16px;
  }

  .navBarList {
    display: flex;
    flex-direction:column;
    gap: 16px;
  }

  .navBarItemGroup {
    display:grid;
    grid-template-rows: 1fr 1fr 1fr;
  }

  .navBarItem {
    display:flex;
    align-items:center;
    border-radius: 100px;
    font-size:14px;
    line-height: 26px;
    gap:20px;

    &:hover {
      background-color: var(--color-gray-lightest);
    }

    &:active {
      background-color: var(--color-primary-lightest);
    }
  }

  .navBarItemIcon {
    display: flex;
    justify-content:space-between ;
    align-items: center;
    background-color: transparent;
    gap: 5px;
    width:20px;
    height: 20px;
  }

  .navBarItemContent {
    background-color:transparent;
  }

  .navBarBodyStorage {
    display: flex;
    flex-direction: column;
    gap: 10px;
    padding: 8px 32px 8px 16px;
    width: 90%;
  }

  .navBarBodyStorageBar {
    background-color: #e9eef6;
    width: 100%;
    line-height:20px;
    height: 5px;
    border-radius: 100px;
  }

  .navBarBodyStorageProgress {
    background-color: var(--color-primary);
    width: 30%;
    line-height:20px;
    height: 5px;
    border-radius: 100px;
  }

  .navBarBodyStorageTitle {
    line-height: 20px;
    font-family: 'Open Sans', sans-serif;
    font-size: 14px;
  }

  .navBarBodyStorageBtn {
    border: 1px solid black;
    color: var(--color-primary);
    border-radius: 20px;
    line-height: 20px;
    font-weight: 600;
    padding: 8px 16px;

    &:hover {
      background-color: #E6EDFA;
    }

    &:active {
      background-color: #E6EDFA;
    }
  }

</style>
