<script setup>
import logo from '@/assets/images/google-drive-logo.png'

const dialogFormVisible = ref(false)
const formLabelWidth = '140px'

const form = reactive({
  name: '',
  file_type: 'Bất kỳ',
  date1: '',
  date2: '',
  delivery: false,
  owner_ship: 'Bất kỳ ai',
  resource: '',
  desc: '',
})
</script>

<template>
  <div :class="$style.headerWrapper">
    <div :class="$style.headerLogoWrapper">
      <img :src="logo" alt="Google Drive Logo" :class="$style.headerLogo">

      <span :class="$style.headerLogoName">Drive</span>
    </div>

    <div :class="$style.headerActionWrapper">
      <form :class="$style.headerSearchWrapper">
        <button :class="[$style.headerSearchBtn, $style.headerBtn]">
          <i class="fa-solid fa-search" :class=" $style.headerIcon" />
        </button>

        <input type="text" :class="$style.headerInput" placeholder="Tìm trong Drive">

        <el-button plain :class="[$style.headerSearchBtn, $style.headerBtn]" @click="dialogFormVisible = true">
          <i class="fa-solid fa-sliders" :class=" $style.headerIcon" />
        </el-button>

        <el-dialog v-model="dialogFormVisible" :class="$style.headerPopUpWrapper" width="70%">
          <el-form :model="form" :class="$style.headerPopUpList">
            <div :class="$style.headerPopUpItem">
              <span :class="$style.headerPopUpItemLabel">Loại</span>

              <el-form-item :label-width="formLabelWidth" :class="$style.headerPopUpItemContent">
                <el-select v-model="form.file_type" placeholder="Please select a zone">
                  <el-option label="Ảnh và hình ảnh" value="image" />
                  <el-option label="PDF" value="pdf" />
                  <el-option label="Tài liệu" value="word" />
                  <el-option label="Bảng tính" value="excel" />
                  <el-option label="Bảng trình bày" value="powerpoint" />
                  <el-option label="Biểu mẫu" value="form" />
                  <el-option label="Video" value="video" />
                  <el-option label="Tệp lưu trữ (Zip)" value="zip" />
                  <el-option label="Bảng vẽ" value="diagram" />
                  <el-option label="Lối tắt" value="shortcut" />
                  <el-option label="Thư mục" value="folder" />
                  <el-option label="Site" value="site" />
                </el-select>
              </el-form-item>
            </div>

            <div :class="$style.headerPopUpItem">
              <span :class="$style.headerPopUpItemLabel">Chủ sở hữu</span>

              <el-form-item :label-width="formLabelWidth" :class="$style.headerPopUpItemContent">
                <el-select v-model="form.owner_ship" placeholder="Please select a zone">
                  <el-option label="Bất kỳ ai" value="any" />

                  <el-option label="Do tôi sở hữu" value="my_own" />

                  <el-option label="không do tôi sở hữu" value="other_own" />

                  <el-option label="Một người cụ thể" value="specific_person" />
                </el-select>
              </el-form-item>
            </div>


          </el-form>

          <template #footer>
            <div class="dialog-footer">
              <el-button @click="dialogFormVisible = false">
                Cancel
              </el-button>
              <el-button type="primary" @click="dialogFormVisible = false">
                Confirm
              </el-button>
            </div>
          </template>
        </el-dialog>
      </form>

      <div :class="$style.headerBtnWrapper">
        <button :class="[$style.headerBtn, $style.headerActionBtn]">
          <i class="fa-regular fa-circle-question" :class=" $style.headerIcon" />
        </button>

        <button :class="[$style.headerBtn, $style.headerActionBtn]">
          <i class="fa-solid fa-gear" :class=" $style.headerIcon" />
        </button>
      </div>
    </div>

    <div :class="$style.headerAccountWrapper">
      <div :class="[$style.headerIcon, $style.headerBtn]">
        <i class="fa-solid fa-list-ul" />
      </div>

      <div class="demo-basic--circle">
        <div class="block" :class="$style.headerAvatar">
          <el-avatar :size="40" :src="circleUrl" />
        </div>

        <div v-for="size in sizeList" :key="size" class="block">
          <el-avatar :size="size" :src="circleUrl" />
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" module>
.headerWrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
  line-height: 27px;
}

.headerLogoWrapper {
  display: flex;
  align-items: center;
  justify-content: flex-start;
  padding-right: 4px;
  flex: 0 0 250px
}

.headerLogo {
  width: 44px;
  height: 40px;
  object-fit:cover;
}

.headerLogoName {
  font-size: 22px;
  line-height: 24px;
  padding-left: 10px;
  font-family: "PT Sans", sans-serif;
  font-weight: 700;
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

.headerSearchWrapper {
  flex: 0 1 750px;
  height: 48px;
  position: relative;
  display: flex;
  align-items: center;
  border: none;
  font-size: 13px;
  line-height:27px;
  background-color: #e9eef6;
  width: 100%;
  padding: 0 10px;
  border-radius: 24px;
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

.headerInput {
  margin: 0 96px 0 56px;
  border: none;
  background-color: transparent;
  max-width: 720px;
}

.headerIcon {
  font-size: 13px;
  padding: 3px;
  color: #444746;
  font-size: 18px;
}

.headerBtn {
  width: 40px;
  height: 40px;
  padding: 8px;
  border: none;
  border-radius: 50%;
  background-color: transparent;
  text-align: center;

  &:hover {
    background-color: #DCE0E8;
  }
}

.headerSearchBtn {
  position: absolute;

  &:first-of-type {
    left: 10px;
    top:50%;
    transform: translateY(-50%);
  }

  &:last-of-type {
    right: 10px;
    top:50%;
    transform: translateY(-50%);
  }
}

.headerAvatar {
  display: flex;
  align-items: center;
}

.headerPopUpWrapper {
  line-height: 20px;
  border-radius:8px;
  padding: 24px 0 0;
  overflow-y: auto;
}

.headerPopUpList {
  padding: 8px 24px 0;
  
  & * {
    font-family: "Open Sans", sans-serif;
    font-weight: 500;
  }
}

.headerPopUpItem{
  display: grid;
  grid-template-columns: 130px 510px;
}

.headerPopUpItemLabel {
  font-weight: 700;
  font-size: 14px;
  line-height:44px;
  letter-spacing: 0.3px;

}

:global(.el-form-item ) {
  margin-bottom: 0;
}

:global(.el-select__wrapper) {
  padding: 0 12px;
  min-height: 42px;
}
</style>
