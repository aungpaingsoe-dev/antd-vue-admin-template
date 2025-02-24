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
        <Menus v-model="selectedKeys" />
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
      <!-- Header -->
      <Header
        :collapsed="collapsed"
        @toggleCollapsed="() => (collapsed = !collapsed)"
      />

      <!-- Content -->
      <a-layout-content>
        <main class="w-[97%] py-3.5 mx-auto"><slot /></main>
      </a-layout-content>
    </a-layout>
  </a-layout>
</template>

<script lang="ts" setup>
import { ref } from "vue";
import Header from "@/components/common/Header.vue";
import Menus from "@/components/common/Menus.vue";
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
