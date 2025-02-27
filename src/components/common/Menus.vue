<script lang="ts" setup>
import {
  SettingOutlined,
  LockOutlined,
  UserOutlined,
  TeamOutlined,
  LayoutOutlined,
  BugOutlined,
} from "@ant-design/icons-vue";

import IconError404 from "@/components/icons/IconError404.vue";
import IconServerOff from "@/components/icons/IconServerOff.vue";

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
    <!-- General -->
    <a-menu-item-group key="g1">
      <template #title>
        <span>General</span>
      </template>
      <a-menu-item key="1">
        <div class="flex items-center">
          <layout-outlined />
          <span>Dashboard</span>
        </div>
      </a-menu-item>
      <a-menu-item key="2">
        <div class="flex items-center">
          <user-outlined />
          <span>Users</span>
        </div>
      </a-menu-item>
    </a-menu-item-group>

    <!-- Team Management Group -->
    <a-menu-item-group key="g2">
      <template #title>
        <span>Other</span>
      </template>
      <a-sub-menu key="sub1">
        <template #title>
          <div class="flex items-center">
            <team-outlined />
            <span>Auth</span>
          </div>
        </template>
        <a-menu-item key="6">
          <div class="flex items-center">
            <LockOutlined />
            <span>Sign In</span>
          </div>
        </a-menu-item>
      </a-sub-menu>
      <a-sub-menu key="sub2">
        <template #title>
          <div class="flex items-center">
            <BugOutlined />
            <span>Errors</span>
          </div>
        </template>
        <a-menu-item key="6">
          <div class="flex items-center gap-2">
            <IconError404 />
            <span>404</span>
          </div>
        </a-menu-item>
        <a-menu-item key="7">
          <div class="flex items-center gap-2">
            <IconServerOff />
            <span>500</span>
          </div>
        </a-menu-item>
      </a-sub-menu>
      <a-menu-item key="sub3">
        <div class="flex items-center">
          <setting-outlined />
          <span>Settings</span>
        </div>
      </a-menu-item>
    </a-menu-item-group>
  </a-menu>
</template>

<style scoped>
/* Optional: Style the group titles */
:deep(.ant-menu-item-group-title) {
  padding-left: 24px;
  color: rgba(0, 0, 0, 0.45);
  font-size: 12px;
  font-weight: 500;
  text-transform: uppercase;
}
</style>
