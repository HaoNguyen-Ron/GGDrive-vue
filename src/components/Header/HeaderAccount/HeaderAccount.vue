<script setup>
const account = {
  email: 'mygmail@gmail.com',
  avatar: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRbNn4d_lU3UW7qa9LBZXxD9VKVCwTq-2wESi364DCN5g&s',
  first_name: 'Arthur',
  last_name: 'Morgan',

}
</script>

<template>
  <div :class="$style.headerAccountWrapper">
    <p :class="$style.headerAccountEmail">
      {{ account.email }}
    </p>

    <a href="/">
      <img :src="account.avatar" alt="user avatar" :class="$style.headerAccountAvatar">
    </a>

    <h1 :class="$style.headerAccountHeader">
      Hello, {{ account.last_name }}
    </h1>

    <button :class="$style.headerAccountBtn">
      <a href="/" :class="$style.headerAccountBtnLink">
        Quản lý tài khoảng của bạn
      </a>
    </button>

    <el-menu
      default-active="2"
      class="el-menu-vertical-demo"
      :class="$style.headerAccountList"
      @open="handleOpen"
      @close="handleClose"
    >
      <el-sub-menu index="1">
        <template #title>
          <el-icon><location /></el-icon>
          <span>Navigator One</span>
        </template>

        <el-menu-item-group title="Group One">
          <el-menu-item index="1-1">
            item one
          </el-menu-item>
          <el-menu-item index="1-2">
            item two
          </el-menu-item>
        </el-menu-item-group>
        <el-menu-item-group title="Group Two">
          <el-menu-item index="1-3">
            item three
          </el-menu-item>
        </el-menu-item-group>
        <el-sub-menu index="1-4">
          <template #title>
            item four
          </template>
          <el-menu-item index="1-4-1">
            item one
          </el-menu-item>
        </el-sub-menu>
      </el-sub-menu>
    </el-menu>
  </div>
</template>

<style lang="scss" module>
    .headerAccountWrapper {
        background-color: rgb(233, 238, 246);
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        border-radius: 30px;
        width: 436px;
        font-family: 'Roboto', sans-serif;
        padding: 8px 12px 16px 12px;
    }

    .headerAccountEmail {
        font-size: 14px;
        font-weight: 500;
        overflow: hidden;
        line-height: 20px;
    }

    .headerAccountAvatar {
        width: 80px;
        height: 80px;
        object-fit: cover;
        border-radius: 50%;
        margin-top: 22px;
    }

    .headerAccountHeader {
        font-size: 22px;
        font-weight: 400;
        line-height: 28px;
        margin: 8px 0;
    }

    .headerAccountBtn {
        margin: 2px 0 16px 0;
        border: 1px solid black;
        border-radius: 99999px;
        line-height: 20px;
        font-weight: 500;
        height: 36px;

        &:hover {
        background-color: #E6EDFA;
        }

        &:active {
        background-color: #E6EDFA;
        }
    }

    .headerAccountBtnLink {
        color: var(--color-primary);
        padding: 9px 23px;
    }

    .headerAccountList {
        width: 100%;
        border-radius: 30px;
    }
</style>
