<script setup>
import logo from '@/assets/images/google-drive-logo.png'
</script>

<template>
  <div :class="$style.headerWrapper">
    <a :class="$style.headerLogoWrapper" href="/">
      <img :src="logo" alt="Google Drive Logo" :class="$style.headerLogo">

      <span :class="$style.headerLogoName">Drive</span>
    </a>

    <div :class="$style.headerActionWrapper">
      <HeaderSearch />

      <div :class="$style.headerBtnWrapper">
        <el-dropdown trigger="click">
          <el-button>
            <i class="fa-regular fa-circle-question" :class=" $style.headerIcon" />
          </el-button>

          <template #dropdown>
            <el-dropdown-menu>
              <el-dropdown-item>Trợ giúp</el-dropdown-item>
              <el-dropdown-item>Đạo tạo</el-dropdown-item>
              <div :class="$style.headerBorderBottom" />
              <el-dropdown-item>Điều khoảng và chính sách</el-dropdown-item>
              <div :class="$style.headerBorderBottom" />
              <el-dropdown-item> Gửi ý kiến phản hồi cho Google</el-dropdown-item>
            </el-dropdown-menu>
          </template>
        </el-dropdown>

        <el-dropdown trigger="click">
          <el-button>
            <i class="fa-solid fa-gear" :class=" $style.headerIcon" />
          </el-button>

          <template #dropdown>
            <el-dropdown-menu>
              <el-dropdown-item>Cài đặt</el-dropdown-item>
              <el-dropdown-item>Tải Drive cho máy tính</el-dropdown-item>
              <el-dropdown-item> Phím tắt</el-dropdown-item>
            </el-dropdown-menu>
          </template>
        </el-dropdown>
      </div>
    </div>

    <div :class="$style.headerAccountWrapper">
      <el-dropdown trigger="click">
        <el-button>
          <i class="fa-solid fa-list-ul" :class="$style.headerIcon" />
        </el-button>

        <template #dropdown>
          <HeaderService />
        </template>
      </el-dropdown>

      <el-dropdown trigger="click">
        <el-button>
          <div class="block" :class="$style.headerAvatar">
            <el-avatar :size="32" />
          </div>
        </el-button>

        <template #dropdown>
          <HeaderAccount />
        </template>
      </el-dropdown>
    </div>
  </div>
</template>

<style lang="scss" module>
.headerWrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
  line-height: 27px;
  margin-bottom: 10px;
  padding: 8px;
}

.headerLogoWrapper {
  display: flex;
  align-items: center;
  justify-content: flex-start;
  flex: 0 0 250px;
  gap: 10px;
  padding-left: 16px;
}

.headerLogo {
  width: 44px;
  height: 40px;
  object-fit:cover;
}

.headerLogoName {
  font-size: 22px;
  line-height: 24px;
  font-family: "PT Sans", sans-serif;
  font-weight: 500;
  font-style: normal;
}

.headerActionWrapper {
  display: flex;
  vertical-align: middle;
  white-space: nowrap;
  justify-content: space-between;
  align-items: center;
  flex: 1 1 auto;
}

.headerBtnWrapper {
  display: flex;
  align-items: center;
  justify-content: flex-end;
}

.headerAccountWrapper  {
  display:flex;
  align-items: center;
  justify-content:center;
  gap: 8px;
}

.headerAvatar {
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
}


.headerIcon {
  font-size: 13px;
  padding: 3px;
  color: #444746;
  font-size: 18px;
  background-color: transparent;
}
</style>
