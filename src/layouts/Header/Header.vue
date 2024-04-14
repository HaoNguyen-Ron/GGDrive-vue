<script setup>
import logo from '@/assets/images/google-drive-logo.png'

const dialogFormVisible = ref(false)
const formLabelWidth = '140px'

const form = reactive({
  name: '',
  file_type: 'any',
  owner_ship: 'any',
  contain_letter: '',
  location: 'any',
  checkList: ref([]),
  auth:  ref([]),
  surveillant:'none',
  share_with: '',
})

const value = ref('2021-10-29')
const holidays = [
  '2021-10-01',
  '2021-10-02',
  '2021-10-03',
  '2021-10-04',
  '2021-10-05',
  '2021-10-06',
  '2021-10-07',
]

function isHoliday({ dayjs }) {
  return holidays.includes(dayjs.format('YYYY-MM-DD'))
}
</script>

<template>
  <div :class="$style.headerWrapper">
    <a :class="$style.headerLogoWrapper" href="/">
      <img :src="logo" alt="Google Drive Logo" :class="$style.headerLogo">

      <span :class="$style.headerLogoName">Drive</span>
    </a>

    <div :class="$style.headerActionWrapper">
      <form :class="$style.headerSearchWrapper">
        <button :class="[$style.headerSearchBtn, $style.headerBtn]">
          <i class="fa-solid fa-search" :class=" $style.headerIcon" />
        </button>

        <input type="text" :class="$style.headerInput" placeholder="Tìm trong Drive">

        <el-button plain :class="[$style.headerSearchBtn, $style.headerBtn]" @click="dialogFormVisible = true">
          <i class="fa-solid fa-sliders" :class=" $style.headerIcon" />
        </el-button>

        <el-dialog v-model="dialogFormVisible" :class="$style.headerPopUpWrapper" width="50%">
          <el-form :model="form" :class="$style.headerPopUpList">
            <div :class="$style.headerPopUpItem">
              <span :class="$style.headerPopUpItemLabel">Loại</span>

              <el-form-item :label-width="formLabelWidth" :class="$style.headerPopUpItemContent" size="large">
                <el-select v-model="form.file_type">
                  <el-option label="Bất kỳ" value="any" />
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

              <div :class="$style.headerPopUpItemContentWrapper">
                <el-form-item :label-width="formLabelWidth" size="large">
                  <el-select v-model="form.owner_ship" placeholder="Please select a zone">
                    <el-option label="Bất kỳ ai" value="any" />

                    <el-option label="Do tôi sở hữu" value="my_own" />

                    <el-option label="không do tôi sở hữu" value="other_own" />

                    <el-option label="Một người cụ thể" value="specific_person" />
                  </el-select>
                </el-form-item>

                <div :class="$style.headerPopUpItemContentOption">
                  <el-form-item :label-width="formLabelWidth">
                    <el-input v-model="form.name" autocomplete="off" size="large" />
                  </el-form-item>
                </div>
              </div>
            </div>

            <div :class="$style.headerPopUpItem">
              <span :class="$style.headerPopUpItemLabel">Có các từ</span>

              <el-form-item :label-width="formLabelWidth">
                <el-input v-model="form.contain_letter" autocomplete="off" placeholder="Nhập các từ tìm thấy trong tệp" size="large" />
              </el-form-item>
            </div>

            <div :class="$style.headerPopUpItem">
              <span :class="$style.headerPopUpItemLabel">Tên mục</span>

              <el-form-item :label-width="formLabelWidth">
                <el-input v-model="form.contain_letter" autocomplete="off" placeholder="Nhập một cụm từ khớp với một phần của tên tệp" size="large" />
              </el-form-item>
            </div>

            <div :class="$style.headerPopUpItem">
              <span :class="$style.headerPopUpItemLabel">Địa điểm</span>

              <div class="headerPopUpItemContentWrapper">
                <el-form-item :label-width="formLabelWidth" :class="$style.headerPopUpItemContent" size="large">
                  <el-select v-model="form.location">
                    <el-option label="Mọi nơi" value="any" />

                    <el-option label="Drive của tôi" value="my_drive" />

                    <el-option label="Được chia sẻ với tôi" value="share_drive" />

                    <el-option label="Vị trí khác" value="other_location" />
                  </el-select>
                </el-form-item>

                <el-form-item :label-width="formLabelWidth" :class="$style.headerPopUpItemContentCheckbox">
                  <el-checkbox-group v-model="checkList" :class="$style.headerPopUpCheckbox" >
                    <el-checkbox label="Trong thùng rác" value="Trash" />
                    <el-checkbox label="Có đánh dấu sao" value="Start" />
                    <el-checkbox label="Đã mã hóa" value="Encript" />
                  </el-checkbox-group>
                </el-form-item>
              </div>
            </div>

            <div :class="$style.headerPopUpItem">
              <span :class="$style.headerPopUpItemLabel">Ngày sửa đổi</span>

              <div class="headerPopUpItemContentWrapper">
                <el-form-item :label-width="formLabelWidth" :class="$style.headerPopUpItemContent" size="large">
                  <el-select v-model="form.file_type">
                    <el-option label="Mọi lúc" value="any" />
                    <el-option label="Hôm nay" value="image" />
                    <el-option label="Hôm qua" value="pdf" />
                    <el-option label="7 ngày qua" value="word" />
                    <el-option label="30 ngày qua" value="excel" />
                    <el-option label="90 ngày qua" value="powerpoint" />
                    <el-option label="Tùy chỉnh" value="form" />
                  </el-select>
                </el-form-item>

                <div :class="$style.headerPopUpItemContentOption">
                  <span :class="$style.headerPopUpItemLabel">Nằm trong khoảng</span>

                  <div :class="$style.headerPopUpItemContentDatePicker">
                    <el-date-picker
                      v-model="value"
                      type="date"
                      placeholder="Sau ngày"
                      format="YYYY/MM/DD"
                      value-format="YYYY-MM-DD"
                      size="large"
                    >
                      <template #default="cell">
                        <div class="cell" :class="{ current: cell.isCurrent }">
                          <span class="text">{{ cell.text }}</span>
                          <span v-if="isHoliday(cell)" class="holiday" />
                        </div>
                      </template>
                    </el-date-picker>

                    <el-date-picker
                      v-model="value"
                      type="date"
                      placeholder="Trước ngày"
                      format="YYYY/MM/DD"
                      value-format="YYYY-MM-DD"
                      size="large"
                    >
                      <template #default="cell">
                        <div class="cell" :class="{ current: cell.isCurrent }">
                          <span class="text">{{ cell.text }}</span>
                          <span v-if="isHoliday(cell)" class="holiday" />
                        </div>
                      </template>
                    </el-date-picker>
                  </div>
                </div>
              </div>
            </div>

            <div :class="$style.headerPopUpItem">
              <span :class="$style.headerPopUpItemLabel">Yêu cầu phê duyệt</span>

              <el-form-item :label-width="formLabelWidth">
                <el-checkbox-group v-model="auth" :class="$style.headerPopUpCheckbox" >
                    <el-checkbox label="Đang chờ tôi phê duyệt" value="pending" />
                    <el-checkbox label="Do tôi yêu cầu" value="request" />
                  </el-checkbox-group>
              </el-form-item>
            </div>

            <div :class="$style.headerPopUpItem">
              <span :class="$style.headerPopUpItemLabel">Đã chia sẻ với tôi</span>

              <el-form-item :label-width="formLabelWidth">
                <el-input v-model="form.share_with" autocomplete="off" placeholder="Nhập tên địa chỉ hoặc email..." size="large" />
              </el-form-item>
            </div>

            <div :class="$style.headerPopUpItem">
              <span :class="$style.headerPopUpItemLabel">Mục cần theo dõi</span>

              <div :class="$style.headerPopUpItemContentWrapper">
                <el-form-item :label-width="formLabelWidth" size="large">
                  <el-select v-model="form.surveillant">
                    <el-option label="-" value="none" />

                    <el-option label="Bất kỳ" value="any" />

                    <el-option label="Chỉ những mục có nội dung để xuất" value="contain_content" />

                    <el-option label="Chỉ những nhận xét được giao cho tôi" value="shared_comment" />
                  </el-select>
                </el-form-item>
              </div>
            </div>
          </el-form>

          <template #footer>
            <div class="dialog-footer" :class="$style.headerPopUpFooter">
              <div class="dialog-footer-left">
                <button @click="dialogFormVisible = false" :class="[$style.headerPopUpFooterBtn, $style.headerPopUpFooterBtnSecondary]">
                  <a href="/">Tìm hiểu thêm</a>
                </button>
              </div>

              <div :class="$style.headerPopUpFooterRight">
                <button @click="dialogFormVisible = false" :class="[$style.headerPopUpFooterBtn, $style.headerPopUpFooterBtnSecondary]">
                  Đặt lại
                </button>

                <button @click="dialogFormVisible = false" :class="[$style.headerPopUpFooterBtn, $style.headerPopUpFooterBtnPrimary]">
                  Tìm kiếm
                </button>
              </div>
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
          <el-avatar :size="32" :src="circleUrl" />
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

.headerSearchWrapper {
  flex: 0 1 750px;
  height: 48px;
  position: relative;
  display: flex;
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
}

.headerInput {
  border: none;
  background-color: transparent;
  background-color: #e9eef6;
  height: 48px;
  position: relative;
  align-items: center;
  border: none;
  font-size: 13px;
  line-height:27px;
  padding: 0 50px;
  border-radius: 24px;
  width: 100%;

  &:focus {
    outline: none;
    border: none;
    background-color: #fff;
    box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
  }
}

.headerIcon {
  font-size: 13px;
  padding: 3px;
  color: #444746;
  font-size: 18px;
  background-color: transparent;
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
  z-index: 2;
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

//-----------------------------------Header PopUp
.headerPopUpWrapper {
  line-height: 20px;
  border-radius:8px;
  padding: 24px 0 0;
  overflow: hidden
}

.headerPopUpList {
  padding: 8px 24px 0;
  display: flex;
  flex-direction: column;
  gap: 20px;
  & * {
    font-family: "Open Sans", sans-serif;
    font-weight: 500;
  }
}

.headerPopUpItem{
  display: grid;
  grid-template-columns: 130px 1fr;
  gap: 20px;
}

.headerPopUpItemLabel {
  font-weight: 700;
  font-size: 14px;
  line-height:44px;
  letter-spacing: 0.3px;
}

.headerPopUpItemContentWrapper {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
}

.headerPopUpItemContent {
  width: 50%;
}

.headerPopUpItemContentCheckbox {
  display: flex;
  flex-wrap: wrap;
  margin-top: 10px;
}

.headerPopUpCheckbox {
  padding-left: 10px;
}

.headerPopUpItemContentDatePicker {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  gap: 15px;
}

.headerPopUpItemContentOption span {
  font-weight: 500;
  font-size: 14px;
  line-height:56px;
  letter-spacing: 0.3px;
}

.headerPopUpFooter {
  display: flex;
  justify-content: space-between;
  padding: 12px 16px 12px 24px;
}

.headerPopUpFooterRight {
  display: flex;
  justify-content:center;
  align-items:center;
  gap: 10px;
}

.headerPopUpFooterBtn {
  font-size: 14px;
  font-weight: 500;
  line-height: 20px;
  text-align:center;
  border-radius:20px;
  padding: 8px 24px;
}

.headerPopUpFooterBtnSecondary {
  color: var(--color-primary);
  background-color: transparent;
  border:none;

  &:hover {
    background-color: var(--color-gray-lighter);
  }

  &:active {
    background-color: var(--color-primary-lighter);
  }
}

.headerPopUpFooterBtnPrimary {
  color: #ddd;
  background-color: var(--color-primary);
  border:none;

  &:hover {
    background-color: var(--color-primary-dark);
  }

  &:active {
    background-color: var(--color-primary-dark);
  }
}

:global(.el-form-item ) {
  margin-bottom: 0;
}

:global(.el-select__wrapper) {
  padding: 0 12px;
}

:global(.el-form-item__content) {
  margin-left: 0 !important;
}

:global(.el-dialog) {
  margin-top: 70px ;
  margin-left: 260px;
}

:global(.el-button>span) {
  background-color: transparent;
}
</style>
