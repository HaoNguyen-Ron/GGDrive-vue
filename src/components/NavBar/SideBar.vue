<script setup lang="ts">

</script>

<template>
  <div :class="$style.sideBarWrapper">
    <div :class="$style.sideBarHeader">
      <button :class="$style.sideBarAddBtn">
        <i class="fa-solid fa-plus" :class="$style.sideBarItemIcon" />
        Mới
      </button>
    </div>

    <div :class="$style.sideBarBody">
      <div :class="$style.sideBarList">
        <div :class="$style.sideBarItemGroup">
          <button :class="[$style.sideBarBtn, $style.sideBarItem]">
            <div :class="$style.sideBarItemIcon">
              <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
              <i class="fa-solid fa-home" />
            </div>

            <span :class="$style.sideBarItemContent">Trang chủ</span>
          </button>

          <button :class="[$style.sideBarBtn, $style.sideBarItem]">
            <div :class="$style.sideBarItemIcon">
              <i class="fa-solid fa-caret-right" />
              <i class="fa-regular fa-hard-drive" />
            </div>

            <span :class="$style.sideBarItemContent">Drive của tôi</span>
          </button>

          <button :class="[$style.sideBarBtn, $style.sideBarItem]">
            <div :class="$style.sideBarItemIcon">
              <i class="fa-solid fa-caret-right" />
              <i class="fa-solid fa-computer" />
            </div>

            <span :class="$style.sideBarItemContent">Máy Tính</span>
          </button>
        </div>

        <div :class="$style.sideBarItemGroup">
          <button :class="[$style.sideBarBtn, $style.sideBarItem]">
            <div :class="$style.sideBarItemIcon">
              <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
              <i class="fa-regular fa-user" />
            </div>

            <span :class="$style.sideBarItemContent">Được chia sẻ với tôi</span>
          </button>

          <button :class="[$style.sideBarBtn, $style.sideBarItem]">
            <div :class="$style.sideBarItemIcon">
              <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
              <i class="fa-regular fa-clock" />
            </div>

            <span :class="$style.sideBarItemContent">Gần đây</span>
          </button>

          <button :class="[$style.sideBarBtn, $style.sideBarItem]">
            <div :class="$style.sideBarItemIcon">
              <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
              <i class="fa-regular fa-star" />
            </div>

            <span :class="$style.sideBarItemContent">Có gắn dấu sao</span>
          </button>
        </div>

        <div :class="$style.sideBarItemGroup">
          <button :class="[$style.sideBarBtn, $style.sideBarItem]">
            <div :class="$style.sideBarItemIcon">
              <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
              <i class="fa-regular fa-circle-xmark" />
            </div>

            <span :class="$style.sideBarItemContent">Nội dung rác</span>
          </button>

          <button :class="[$style.sideBarBtn, $style.sideBarItem]">
            <div :class="$style.sideBarItemIcon">
              <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
              <i class="fa-regular fa-trash-can" />
            </div>

            <span :class="$style.sideBarItemContent">Thùng rác</span>
          </button>

          <button :class="[$style.sideBarBtn, $style.sideBarItem]">
            <div :class="$style.sideBarItemIcon">
              <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
              <i class="fa-solid fa-cloud" />
            </div>

            <span :class="$style.sideBarItemContent">Bộ nhớ</span>
          </button>
        </div>
      </div>

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
  }

  .sideBarHeader {
    padding: 8px 16px 16px 0;
  }

  .sideBarAddBtn {
    display: flex;
    align-items:center;
    justify-content: flex-start;
    gap: 12px;
    border-radius: 16px;
    box-shadow:  rgba(0, 0, 0, 0.3) 0px 4px 6px 0px;
    padding: 18px 20px 18px 16px;
    background-color: #ffffff;
    font-family: 'Arial', sans-serif;
    text-align:center;
    font-weight: 500;
    line-height:20px;
    color: #1f1f1f;
    font-size: 14px;
    cursor: pointer;
    min-width: 100px;

    &:hover {
      background-color: #e9eef6;
    }
  }

  .sideBarBtn {
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
    width: 224px;
    height: 32px;
  }

  .sideBarBody {
    padding: 8px 0 16px;
  }

  .sideBarList {
    display: flex;
    flex-direction:column;
    gap: 16px;
  }

  .sideBarItemGroup {
    display:grid;
    grid-template-rows: 1fr 1fr 1fr;
  }

  .sideBarItem {
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

  .sideBarItemIcon {
    display: flex;
    justify-content:space-between ;
    align-items: center;
    background-color: transparent;
    gap: 5px;
    width:20px;
    height: 20px;
  }

  .sideBarItemContent {
    background-color:transparent;
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
      background-color: #E6EDFA;
    }

    &:active {
      background-color: #E6EDFA;
    }
  }
</style>
