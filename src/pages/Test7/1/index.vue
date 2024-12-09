<template>
  <view class="container">
    <view class="menu">
      <text class="menu-title">单元格</text>
      <view class="menu-content">
        <view class="menu-item" @click="toggleSubMenu('basic')">页面导航</view>
        <view v-if="subMenu.basic" class="sub-menu">
          <view class="sub-menu-item">页面导航</view>
          <view class="sub-menu-item">URL 跳转</view>
          <view class="sub-menu-item">路由跳转</view>
        </view>
        <view class="menu-item" @click="toggleSubMenu('radio')">分组标题</view>
        <radio-group v-if="subMenu.radio" class="sub-menu">
          <radio class="sub-menu-item" value="1">分组 1</radio>
          <radio class="sub-menu-item" value="2">分组 2</radio>
        </radio-group>
        <view class="menu-item" @click="toggleSubMenu('button')">使用指南</view>
        <view v-if="subMenu.button" class="sub-menu">
          <button class="sub-menu-item">使用指南</button>
        </view>
      </view>
    </view>
    <view class="search-bar">
      <input type="text" placeholder="单元格" />
      <button>搜索</button>
    </view>
  </view>
</template>

<script lang="tsx" setup>
import { ref } from 'vue';

const subMenu = ref({
  basic: false,
  radio: false,
  button: false
});

const toggleSubMenu = (menu) => {
  subMenu.value[menu] = !subMenu.value[menu];
};
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  background-color: #f8f8f8;
}

.menu {
  margin-top: 10px;
}

.menu-title {
  font-size: 16px;
  font-weight: bold;
  padding: 10px;
  background-color: #ffffff;
}

.menu-content {
  background-color: #ffffff;
}

.menu-item {
  padding: 10px;
  border-bottom: 1px solid #eaeaea;
  cursor: pointer;
}

.sub-menu {
  display: none;
  background-color: #f2f2f2;
}

.sub-menu-item {
  padding: 10px;
  border-bottom: 1px solid #eaeaea;
}

.radio-group {
  display: flex;
  flex-direction: column;
}

.radio {
  margin: 10px;
  size: default;
}

.search-bar {
  display: flex;
  justify-content: space-between;
  padding: 10px;
  background-color: #ffffff;
  margin-top: 10px;
}

input[type="text"] {
  flex: 1;
  border: 1px solid #eaeaea;
  padding: 10px;
  margin-right: 10px;
}

button {
  padding: 10px;
  background-color: #007aff;
  color: white;
  border: none;
  cursor: pointer;
}
</style>

