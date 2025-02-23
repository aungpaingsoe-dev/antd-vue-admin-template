<template>
  <a-layout>
    <a-layout-sider
      class="m-[5px] rounded-lg overflow-hidden shadow-sm h-[calc(100vh-10px)]"
      width="256"
      collapsedWidth="60"
      :style="{
        background: '#fff',
        position: 'fixed',
        top: '0px',
      }"
      v-model:collapsed="collapsed"
      :trigger="null"
      collapsible
    >
      <div>
        <!-- Logo -->
        <div
          class="py-4 flex items-center w-[90%] mx-auto"
          :class="!collapsed ? 'justify-between' : 'justify-center'"
        >
          <div class="flex gap-2">
            <img
              src="../assets/logo.svg"
              class="h-[32px] w-[32px] rounded-sm"
              alt=""
            />
            <div v-if="!collapsed">
              <div class="font-semibold text-md">Antd Admin</div>
              <div class="text-xs text-gray-500">Superadmin</div>
            </div>
          </div>
        </div>
        <!-- Menus -->
        <a-menu v-model:selectedKeys="selectedKeys" mode="inline">
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
      </div>
    </a-layout-sider>
    <a-layout
      :class="`transition-all duration-300 px-2 ${
        collapsed ? 'ml-[60px]' : 'ml-[256px]'
      }`"
      :style="{
        background: '#fff',
      }"
    >
      <a-layout-header
        class="rounded-lg shadow-sm sticky top-0 flex items-center"
        :style="{
          background: '#fff',
          padding: '0 0 0 10px',
          marginTop: '5px',
        }"
      >
        <div
          v-if="collapsed"
          class="trigger cursor-pointer hover:bg-gray-100 p-2 rounded-lg"
          @click="() => (collapsed = !collapsed)"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="20"
            height="20"
            viewBox="0 0 16 16"
          >
            <path
              fill="currentColor"
              fill-rule="evenodd"
              d="M11.5 2.5H13a.5.5 0 0 1 .5.5v10a.5.5 0 0 1-.5.5h-1.5zm-1.5 0H3a.5.5 0 0 0-.5.5v10a.5.5 0 0 0 .5.5h7zM1 3a2 2 0 0 1 2-2h10a2 2 0 0 1 2 2v10a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2z"
              clip-rule="evenodd"
            />
          </svg>
        </div>

        <div
          v-else
          class="trigger cursor-pointer hover:bg-gray-100 p-2 rounded-lg"
          @click="() => (collapsed = !collapsed)"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="20"
            height="20"
            viewBox="0 0 16 16"
          >
            <path
              fill="currentColor"
              fill-rule="evenodd"
              d="M6 2.5h7a.5.5 0 0 1 .5.5v10a.5.5 0 0 1-.5.5H6zm-1.5 0H3a.5.5 0 0 0-.5.5v10a.5.5 0 0 0 .5.5h1.5zM1 3a2 2 0 0 1 2-2h10a2 2 0 0 1 2 2v10a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2z"
              clip-rule="evenodd"
            />
          </svg>
        </div>
      </a-layout-header>
      <a-layout-content>
        <main class="w-[97%] py-3.5 mx-auto">Content</main>
      </a-layout-content>
    </a-layout>
  </a-layout>
</template>

<script lang="ts" setup>
import { ref } from "vue";
import {
  UserOutlined,
  VideoCameraOutlined,
  UploadOutlined,
  MenuUnfoldOutlined,
  MenuFoldOutlined,
} from "@ant-design/icons-vue";
const selectedKeys = ref<string[]>(["1"]);
const collapsed = ref<boolean>(false);
</script>
<style>
#components-layout-demo-custom-trigger .trigger {
  font-size: 18px;
  line-height: 64px;
  padding: 0 24px;
  cursor: pointer;
  transition: color 0.3s;
}

#components-layout-demo-custom-trigger .trigger:hover {
  color: #1890ff;
}

#components-layout-demo-custom-trigger .logo {
  height: 32px;
  background: rgba(255, 255, 255, 0.3);
  margin: 16px;
}

.site-layout .site-layout-background {
  background: #fff;
}
</style>
