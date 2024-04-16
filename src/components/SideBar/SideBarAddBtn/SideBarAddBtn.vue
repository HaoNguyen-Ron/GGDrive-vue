<script setup>
const dropdownVisible = ref(false)

function toggleDropdown() {
  dropdownVisible.value = !dropdownVisible.value
};

</script>

<template>
  <button :class="$style.sideBarAddBtn" @click="toggleDropdown">
    <i class="fa-solid fa-plus" :class="$style.sideBarAddBtnIcon" />

    <span :class="$style.sideBarAddBtnTitle">Mới</span>
  </button>

    <ul v-if="dropdownVisible" :class="$style.sideBarDropdownList">
      <li :class="$style.sideBarDropdownItem">
        <div :class="$style.sideBarDropdownItemIcon">
          <i class="fa-solid fa-folder-plus" />
        </div>

        <span :class="$style.sideBarDropdownItemTitle">
          Thư mục mới
        </span>
      </li>

      <div :class="$style.sideBarBorderBottom" />

      <li :class="$style.sideBarDropdownItem">
        <div :class="$style.sideBarDropdownItemIcon">
          <i class="fa-solid fa-file-arrow-up" />
        </div>

        <span :class="$style.sideBarDropdownItemTitle">
          Tải tệp lên
        </span>
      </li>

      <li :class="$style.sideBarDropdownItem">
        <div :class="$style.sideBarDropdownItemIcon">
          <i class="fa-regular fa-folder-open" />
        </div>

        <span :class="$style.sideBarDropdownItemTitle">
          Tải thư mục lên
        </span>
      </li>

      <div :class="$style.sideBarBorderBottom" />

      <li :class="$style.sideBarDropdownItem">
        <div :class="$style.sideBarDropdownItemIcon">
          <img src="@/assets/images/google-icon/gg-doc.png" alt="" :class="$style.sideBarDropdownItemImage">
        </div>

        <span :class="[$style.sideBarDropdownItemTitle, $style.sideBarDropdownChild]">
          Google tài liệu

          <button :class=" $style.sideBarExpandBtn">
            <i class="fa-solid fa-caret-right" />
          </button>
        </span>
      </li>

      <li :class="$style.sideBarDropdownItem">
        <div :class="$style.sideBarDropdownItemIcon">
          <img src="@/assets/images/google-icon/gg-excel.png" alt="" :class="$style.sideBarDropdownItemImage">
        </div>

        <span :class="[$style.sideBarDropdownItemTitle, $style.sideBarDropdownChild]">
          Google trang tính

          <button :class=" $style.sideBarExpandBtn">
            <i class="fa-solid fa-caret-right" />
          </button>
        </span>
      </li>

      <li :class="$style.sideBarDropdownItem">
        <div :class="$style.sideBarDropdownItemIcon">
          <img src="@/assets/images/google-icon/gg-slide.png" alt="" :class="$style.sideBarDropdownItemImage">
        </div>

        <span :class="[$style.sideBarDropdownItemTitle, $style.sideBarDropdownChild]">
          Google trang trình bày

          <button :class=" $style.sideBarExpandBtn">
            <i class="fa-solid fa-caret-right" />
          </button>
        </span>
      </li>

      <li :class="$style.sideBarDropdownItem">
        <div :class="$style.sideBarDropdownItemIcon" />

        <span :class="[$style.sideBarDropdownItemTitle, $style.sideBarDropdownChild]">
          Ứng dụng khác

          <button :class=" $style.sideBarExpandBtn">
            <i class="fa-solid fa-caret-right" />
          </button>
        </span>
      </li>
    </ul>
</template>

<style lang="scss" module>
.sideBarAddBtn {
  display: flex;
  align-items:center;
  justify-content: center;
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
  position: relative;

  &:hover {
    background-color: #e9eef6;
  }
}

.sideBarAddBtnIcon {
  display: flex;
  justify-content:center ;
  align-items: center;
  background-color: transparent;
  line-height: 24px;
}

.sideBarAddBtnTitle {
  font-size: 14px;
  font-weight: 500;
  line-height: 20px;
  text-align: center;
}

.sideBarDropdownList {
  font-family: 'Roboto', 'Open Sans', sans-serif;
  position: absolute;
  padding: 8px 0;
  width: 320px;
  border-radius: 5px;
  background-color: #ffffff;
  box-shadow:  rgba(0, 0, 0, 0.3) 0px 4px 6px 0px;
}

.sideBarDropdownItem {
  padding: 0 12px;
  min-height: 32px;
  min-width: 200px;
  display: flex;
  align-items: center;
  justify-content: flex-start;

  &:hover {
    background-color: var(--color-hover);
  }
}

.sideBarDropdownItemIcon {
  flex: 0 0 32px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 16px;
}

.sideBarDropdownItemImage {
  width: 30px;
  height:30px;
}

.sideBarDropdownItemTitle {
  flex: 1 1 auto;
  font-size: 14px;
  font-weight: 400;
  line-height: 20px;
}

.sideBarDropdownChild {
  display: flex;
  justify-content: space-between;
  align-items: center
}

.sideBarBorderBottom {
  margin: 5px 0;
  border: 0.5px solid rgb(199, 199, 199)
}

.sideBarExpandBtn {
  border-radius: 50%;
  width: 25px;
  height:25px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 16px;
  background-color: transparent;

  &:hover {
    background-color: var( --color-gray-light);
  }
}
</style>
