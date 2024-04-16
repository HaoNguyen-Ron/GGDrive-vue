<script setup>
const account = {
  email: 'mygmail@gmail.com',
  avatar: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRbNn4d_lU3UW7qa9LBZXxD9VKVCwTq-2wESi364DCN5g&s',
  first_name: 'Arthur',
  last_name: 'Morgan',
}

const subAccounts = [
  {
    email: 'anothergmail@gmail.com',
    avatar: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRAWLUtIIEmlMvMJRpmjzInpJQpKCommIwuTQ&s',
    first_name: 'Geralt',
    last_name: 'Rivia',
  },
  {
    email: 'andanothergmail@gmail.com',
    avatar: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRenSktYU-a2W_aRVPU9QdR3fnssN_bFgUraw&s',
    first_name: 'Giga',
    last_name: 'Chad',
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
    >
      <el-sub-menu>
        <template #title>
          <span> Hiện thêm tài khoản</span>
        </template>

        <el-menu-item-group :class="$style.headerAccountList">
          <div v-for="(account, index) in subAccounts" :key="index" :class="$style.headerAccountSubList">
            <img :src="account.avatar" alt="user avatar" :class="$style.headerAccountSubAvatar">

            <div :class="$style.headerAccountSubUserDetail">
              <p :class="$style.headerAccountSubUserName">
                {{ `${account.first_name} ${account.last_name}` }}
              </p>

              <p :class="$style.headerAccountSubUserEmail">
                {{ account.email }}
              </p>
            </div>
          </div>

          <div :class="$style.headerAccountSubList">
            <i class="fa-solid fa-plus" :class="$style.headerAccountSubIcon" />

            <span :class="$style.headerAccountSubTitle">
              Thêm tài khoản khác
            </span>
          </div>

          <div :class="$style.headerAccountSubList">
            <i class="fa-solid fa-arrow-right-from-bracket" :class="$style.headerAccountSubIcon" />

            <span :class="$style.headerAccountSubTitle">
              Đăng xuất khỏi tất cả tài khoản
            </span>
          </div>
        </el-menu-item-group>
      </el-sub-menu>
    </el-menu>

    <div :class="$style.headerAccountPolicy">
      <div :class="$style.headerAccountPolicyItem">
        <a href="/">Chính sách quyền riêng tư</a>
      </div>

      <div :class="$style.headerAccountPolicyItem">
        <a href="/">Điều khoảng dịch vụ</a>
      </div>
    </div>
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
        height: 40px;
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

    .headerAccountSubList {
      display: flex;
      justify-content: flex-start;
      align-items: center;
      border-top: 1px solid var(--color-gray-lightest);
      height: 56px;
      padding: 10px 15px 10px 20px;

      &:hover {
        background-color: var(--color-hover);
      }
    }

    .headerAccountSubUserDetail {
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      margin-left: 12px;
    }
     .headerAccountSubTitle {
      margin-left: 12px;
      font-size: 14px;
      font-weight: 500;
      line-height: 20px;
      text-align:left;
      text-wrap: nowrap
     }

    .headerAccountSubAvatar {
      width: 32px;
      height:32px;
      border-radius: 50%;
    }

    .headerAccountSubIcon {
      background-color: #e9eef6;
      border-radius: 50%;
      color: var(--color-primary);
      font-size: 12px;
      padding: 6px;
      margin: 4px;
    }

    .headerAccountSubUserName {
      font-size: 14px;
      font-weight: 500;
      line-height: 20px;
      text-align:left;
      text-wrap: nowrap
    }

    .headerAccountSubUserEmail {
      font-size: 12px;
      line-height: 16px;
      margin-top: 2px;
      font-weight: 400;
    }

    .headerAccountPolicy {
      display: flex;
      justify-content: space-evenly;
      align-items: center;
      gap: 16px;
      padding-top: 20px;
    }

    .headerAccountPolicyItem {
      padding: 5px 4px;
      text-align: right;

      &:last-child::before{
        content:"●";
        margin-right: 20px;
        color: rgba(0, 0, 0, .87);
      }
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

    :global(.el-menu-item) {
      &:hover {
        background-color: var(--color-hover);
      }
    }

    :global(.el-dropdown__list) {
      border-bottom-left-radius: 30px;
      border-bottom-right-radius: 30px;
    }

    :global(.el-menu-item-group__title) {
      padding: 0;
    }
</style>
