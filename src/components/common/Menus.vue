<script lang="ts" setup>
import {
  UserOutlined,
  VideoCameraOutlined,
  UploadOutlined,
} from "@ant-design/icons-vue";
const selectedKeys = defineModel("selectedKeys");
</script>

<template>
  <a-menu
    v-model:selectedKeys="selectedKeys"
    mode="inline"
    :style="{
      shadow: 'none',
      border: 'none',
    }"
  >
    <a-menu-item key="1">
      <user-outlined />
      <span>nav 1</span>
    </a-menu-item>
    <a-menu-item key="2">
      <video-camera-outlined />
      <span>nav 2</span>
    </a-menu-item>
    <a-menu-item key="3">
      <upload-outlined />
      <span>nav 3</span>
    </a-menu-item>
    <a-sub-menu key="sub2">
      <template #title>
        <span>
          <team-outlined />
          <span>Team</span>
        </span>
      </template>
      <a-menu-item key="6">Team 1</a-menu-item>
      <a-menu-item key="8">Team 2</a-menu-item>
    </a-sub-menu>
  </a-menu>
</template>
