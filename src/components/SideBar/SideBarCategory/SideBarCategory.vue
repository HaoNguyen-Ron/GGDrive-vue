<script setup>
const activeDrive = ref(['0'])
const activePc = ref(['0'])
const activeDriveChild = ref(['0'])
</script>

<template>
  <div :class="$style.sideBarCategoryList">
    <div :class="$style.sideBarCategoryGroup">
      <button :class="[$style.sideBarBtn, $style.sideBarCategory]">
        <div :class="$style.sideBarCategoryIcon">
          <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
          <i class="fa-solid fa-home" />
        </div>

        <span :class="$style.sideBarCategoryContent">Trang chủ</span>
      </button>

      <el-collapse v-model="activeDrive">
        <el-collapse-item name="1">
          <template #title>
            <button :class="[$style.sideBarBtn, $style.sideBarCategory]">
              <div :class="$style.sideBarCategoryIcon">
                <i class="fa-solid fa-caret-right" />
                <i class="fa-regular fa-hard-drive" />
              </div>

              <span :class="$style.sideBarCategoryContent">Drive của tôi</span>
            </button>
          </template>

          <el-collapse v-model="activeDriveChild" accordion name="1">
            <el-collapse-item name="1">
              <template #title>
                <button :class="[$style.sideBarBtn, $style.sideBarCategory, $style.sideBarCollapseChild]">
                  <div :class="$style.sideBarCategoryIcon">
                    <i class="fa-solid fa-caret-right" />
                    <i class="fa-regular fa-folder-open" />
                  </div>

                  <span :class="$style.sideBarCategoryContent">Folder Child</span>
                </button>
              </template>

              <button :class="[$style.sideBarBtn, $style.sideBarCategory, $style.sideBarCollapseChild]" name="1">
                <div :class="[$style.sideBarCategoryIcon, $style.sideBarCollapseChild]">
                  <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
                  <i class="fa-regular fa-folder-open" />
                </div>

                <span :class="[$style.sideBarCategoryContent, $style.sideBarCollapseChild]">Folder 1</span>
              </button>

              <button :class="[$style.sideBarBtn, $style.sideBarCategory, $style.sideBarCollapseChild]" name="2">
                <div :class="[$style.sideBarCategoryIcon, $style.sideBarCollapseChild]">
                  <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
                  <i class="fa-regular fa-folder-open" />
                </div>

                <span :class="[$style.sideBarCategoryContent, $style.sideBarCollapseChild]">Folder 1</span>
              </button>

              <button :class="[$style.sideBarBtn, $style.sideBarCategory, $style.sideBarCollapseChild]">
                <div :class="[$style.sideBarCategoryIcon, $style.sideBarCollapseChild]">
                  <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
                  <i class="fa-regular fa-folder-open" />
                </div>

                <span :class="[$style.sideBarCategoryContent, $style.sideBarCollapseChild]">Folder 1</span>
              </button>

            </el-collapse-item>
          </el-collapse>

          <el-collapse v-model="activeDriveChild" accordion name="2">
            <el-collapse-item name="1">
              <template #title>
                <button :class="[$style.sideBarBtn, $style.sideBarCategory, $style.sideBarCollapseChild]">
                  <div :class="$style.sideBarCategoryIcon">
                    <i class="fa-solid fa-caret-right" />
                    <i class="fa-regular fa-folder-open" />
                  </div>

                  <span :class="$style.sideBarCategoryContent">Folder Child</span>
                </button>
              </template>

              <button :class="[$style.sideBarBtn, $style.sideBarCategory, $style.sideBarCollapseChild]">
                <div :class="[$style.sideBarCategoryIcon, $style.sideBarCollapseChild]">
                  <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
                  <i class="fa-regular fa-folder-open" />
                </div>

                <span :class="[$style.sideBarCategoryContent, $style.sideBarCollapseChild]">Folder 1</span>
              </button>

              <button :class="[$style.sideBarBtn, $style.sideBarCategory, $style.sideBarCollapseChild]">
                <div :class="[$style.sideBarCategoryIcon, $style.sideBarCollapseChild]">
                  <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
                  <i class="fa-regular fa-folder-open" />
                </div>

                <span :class="[$style.sideBarCategoryContent, $style.sideBarCollapseChild]">Folder 1</span>
              </button>

              <button :class="[$style.sideBarBtn, $style.sideBarCategory, $style.sideBarCollapseChild]">
                <div :class="[$style.sideBarCategoryIcon, $style.sideBarCollapseChild]">
                  <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
                  <i class="fa-regular fa-folder-open" />
                </div>

                <span :class="[$style.sideBarCategoryContent, $style.sideBarCollapseChild]">Folder 1</span>
              </button>

            </el-collapse-item>
          </el-collapse>
        </el-collapse-item>
      </el-collapse>

      <el-collapse v-model="activePc">
        <el-collapse-item name="1">
          <template #title>
            <button :class="[$style.sideBarBtn, $style.sideBarCategory]">
              <div :class="$style.sideBarCategoryIcon">
                <i class="fa-solid fa-caret-right" />
                <i class="fa-solid fa-computer" />
              </div>

              <span :class="$style.sideBarCategoryContent">Máy tính</span>
            </button>
          </template>

          <el-collapse v-model="activeDriveChild" accordion name="1">
            <el-collapse-item name="1">
              <template #title>
                <button :class="[$style.sideBarBtn, $style.sideBarCategory, $style.sideBarCollapseChild]">
                  <div :class="$style.sideBarCategoryIcon">
                    <i class="fa-solid fa-caret-right" />
                    <i class="fa-regular fa-folder-open" />
                  </div>

                  <span :class="$style.sideBarCategoryContent">Folder Child</span>
                </button>
              </template>

              <button :class="[$style.sideBarBtn, $style.sideBarCategory, $style.sideBarCollapseChild]" name="1">
                <div :class="[$style.sideBarCategoryIcon, $style.sideBarCollapseChild]">
                  <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
                  <i class="fa-regular fa-folder-open" />
                </div>

                <span :class="[$style.sideBarCategoryContent, $style.sideBarCollapseChild]">Folder 1</span>
              </button>

              <button :class="[$style.sideBarBtn, $style.sideBarCategory, $style.sideBarCollapseChild]" name="2">
                <div :class="[$style.sideBarCategoryIcon, $style.sideBarCollapseChild]">
                  <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
                  <i class="fa-regular fa-folder-open" />
                </div>

                <span :class="[$style.sideBarCategoryContent, $style.sideBarCollapseChild]">Folder 1</span>
              </button>

              <button :class="[$style.sideBarBtn, $style.sideBarCategory, $style.sideBarCollapseChild]">
                <div :class="[$style.sideBarCategoryIcon, $style.sideBarCollapseChild]">
                  <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
                  <i class="fa-regular fa-folder-open" />
                </div>

                <span :class="[$style.sideBarCategoryContent, $style.sideBarCollapseChild]">Folder 1</span>
              </button>

            </el-collapse-item>
          </el-collapse>

          <el-collapse v-model="activeDriveChild" accordion name="2">
            <el-collapse-item name="1">
              <template #title>
                <button :class="[$style.sideBarBtn, $style.sideBarCategory, $style.sideBarCollapseChild]">
                  <div :class="$style.sideBarCategoryIcon">
                    <i class="fa-solid fa-caret-right" />
                    <i class="fa-regular fa-folder-open" />
                  </div>

                  <span :class="$style.sideBarCategoryContent">Folder Child</span>
                </button>
              </template>

              <button :class="[$style.sideBarBtn, $style.sideBarCategory, $style.sideBarCollapseChild]">
                <div :class="[$style.sideBarCategoryIcon, $style.sideBarCollapseChild]">
                  <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
                  <i class="fa-regular fa-folder-open" />
                </div>

                <span :class="[$style.sideBarCategoryContent, $style.sideBarCollapseChild]">Folder 1</span>
              </button>

              <button :class="[$style.sideBarBtn, $style.sideBarCategory, $style.sideBarCollapseChild]">
                <div :class="[$style.sideBarCategoryIcon, $style.sideBarCollapseChild]">
                  <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
                  <i class="fa-regular fa-folder-open" />
                </div>

                <span :class="[$style.sideBarCategoryContent, $style.sideBarCollapseChild]">Folder 1</span>
              </button>

              <button :class="[$style.sideBarBtn, $style.sideBarCategory, $style.sideBarCollapseChild]">
                <div :class="[$style.sideBarCategoryIcon, $style.sideBarCollapseChild]">
                  <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
                  <i class="fa-regular fa-folder-open" />
                </div>

                <span :class="[$style.sideBarCategoryContent, $style.sideBarCollapseChild]">Folder 1</span>
              </button>

            </el-collapse-item>
          </el-collapse>
        </el-collapse-item>
      </el-collapse>
    </div>

    <div :class="$style.sideBarCategoryGroup">
      <button :class="[$style.sideBarBtn, $style.sideBarCategory]">
        <div :class="$style.sideBarCategoryIcon">
          <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
          <i class="fa-regular fa-user" />
        </div>

        <span :class="$style.sideBarCategoryContent">Được chia sẻ với tôi</span>
      </button>

      <button :class="[$style.sideBarBtn, $style.sideBarCategory]">
        <div :class="$style.sideBarCategoryIcon">
          <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
          <i class="fa-regular fa-clock" />
        </div>

        <span :class="$style.sideBarCategoryContent">Gần đây</span>
      </button>

      <button :class="[$style.sideBarBtn, $style.sideBarCategory]">
        <div :class="$style.sideBarCategoryIcon">
          <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
          <i class="fa-regular fa-star" />
        </div>

        <span :class="$style.sideBarCategoryContent">Có gắn dấu sao</span>
      </button>
    </div>

    <div :class="$style.sideBarCategoryGroup">
      <button :class="[$style.sideBarBtn, $style.sideBarCategory]">
        <div :class="$style.sideBarCategoryIcon">
          <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
          <i class="fa-regular fa-circle-xmark" />
        </div>

        <span :class="$style.sideBarCategoryContent">Nội dung rác</span>
      </button>

      <button :class="[$style.sideBarBtn, $style.sideBarCategory]">
        <div :class="$style.sideBarCategoryIcon">
          <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
          <i class="fa-regular fa-trash-can" />
        </div>

        <span :class="$style.sideBarCategoryContent">Thùng rác</span>
      </button>

      <button :class="[$style.sideBarBtn, $style.sideBarCategory]">
        <div :class="$style.sideBarCategoryIcon">
          <i class="fa-solid fa-caret-right" :style="{ opacity: '0' }" />
          <i class="fa-solid fa-cloud" />
        </div>

        <span :class="$style.sideBarCategoryContent">Bộ nhớ</span>
      </button>
    </div>
  </div>
</template>

<style lang="scss" module>
      .sideBarCategoryList {
    display: flex;
    flex-direction:column;
    gap: 16px;
  }

  .sideBarCategoryGroup {
    display:flex;
    flex-direction: column
  }

  .sideBarCategory {
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

  .sideBarCategoryIcon {
    display: flex;
    justify-content:space-between ;
    align-items: center;
    background-color: transparent;
    gap: 5px;
    width:20px;
    height: 20px;
  }

  .sideBarCategoryContent {
    background-color:transparent;
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

  .sideBarCollapseChild {
    padding-left: 20px;
  }

  :global(.el-collapse-item__header) {
    background-color: transparent;
    border-bottom: none;
    height: 32px;
  }

  :global(.el-collapse-item__content) {
    padding-bottom: 0;
  }

  :global(.el-collapse) {
    border: none;
    border-bottom: none;
  }

  :global(.el-collapse-item__wrap ) {
    background-color: transparent;
    border: none;
  }

  :global(.el-icon) {
    display: none;
  }
</style>
