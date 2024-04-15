<script setup>
const account = {
  email: 'mygmail@gmail.com',
  avatar: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRbNn4d_lU3UW7qa9LBZXxD9VKVCwTq-2wESi364DCN5g&s',
  first_name: 'Arthur',
  last_name: 'Morgan',
}

const subAccount = [
  {
    email: 'anothergmail@gmail.com',
    avatar: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRbNn4d_lU3UW7qa9LBZXxD9VKVCwTq-2wESi364DCN5g&s',
    first_name: 'Geralt',
    last_name: 'Rivia',
  },
  {
    email: 'andanothergmail@gmail.com',
    avatar: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRbNn4d_lU3UW7qa9LBZXxD9VKVCwTq-2wESi364DCN5g&s',
    first_name: 'Lara',
    last_name: 'Croft',
  },
]
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
        Quản lý tài khoản của bạn
      </a>
    </button>

    <el-menu
      default-active="2"
      class="el-menu-vertical-demo"
      :class="$style.headerAccountUsers"
      @open="handleOpen"
      @close="handleClose"
    >
      <el-sub-menu index="1">
        <template #title>
          <el-icon><location /></el-icon>
          <span>Navigator One</span>
        </template>

        <el-menu-item-group :class="$style.headerAccountList">
          <el-menu-item index="1-1">
            item one
          </el-menu-item>
          <el-menu-item index="1-2">
            item two
          </el-menu-item>
        </el-menu-item-group>
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
        padding: 8px 28px 16px 28px;
    }

    .headerAccountEmail {
        font-size: 14px;
        font-weight: 500;
        overflow: hidden;
        line-height: 20px;
        padding: 18px 0;
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
        background-color: transparent;

        &:hover {
        background-color: #cddbf5;
        }

        &:active {
        background-color: #E6EDFA;
        }
    }

    .headerAccountBtnLink {
        color: var(--color-primary);
        padding: 9px 23px;
    }

    .headerAccountUsers {
        width: 100%;
        border-radius: 30px;
    }

    .headerAccountList {
      border-bottom-right-radius: 30px;
      border-bottom-left-radius: 30px;
    }

    :global(.el-sub-menu__title){
      border-top-left-radius: 30px;
      border-top-right-radius: 30px;
      &:hover {
        background-color: var(--color-hover);
      }

      &:active {
        background-color: var(--color-hover);
      }
    }

    :global(.el-sub-menu){
        border-bottom-left-radius: 30px;
        border-bottom-right-radius: 30px;

        &:hover {
          border-radius: 30px;
        }

        &:active {
          border-radius: 30px;
        }
    }

    :global(.el-menu) {
      border-bottom-left-radius: 30px;
      border-bottom-right-radius: 30px;
    }

    :global(.el-dropdown__list) {
      border-bottom-left-radius: 30px;
      border-bottom-right-radius: 30px;
    }
</style>
