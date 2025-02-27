<script lang="ts" setup>
const { collapsed } = defineProps(["collapsed"]);
</script>

<template>
  <a-layout-header
    class="rounded-lg shadow-sm sticky top-0 flex items-center justify-between"
    :style="{
      background: '#fff',
      marginTop: '5px',
      paddingLeft: '10px',
      paddingRight: '10px',
    }"
  >
    <div>
      <div
        v-if="collapsed"
        class="trigger cursor-pointer hover:bg-gray-100 p-2 rounded-lg"
        @click="$emit('toggleCollapsed')"
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
        @click="$emit('toggleCollapsed')"
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
    </div>

    <a-dropdown :trigger="['click']" class="cursor-pointer">
      <a-avatar size="large" src="/avatartion.png" />
      <template #overlay>
        <a-menu>
          <a-menu-item key="0">
            <div>
              <div class="font-bold">Antd Vue Admin</div>
              <div class="opacity-70 text-sm">antdvueadmin@gmail.com</div>
            </div>
          </a-menu-item>
          <a-menu-divider />
          <a-menu-item key="1">
            <div>
              Profile
            </div>
          </a-menu-item>
          <a-menu-item key="2"> Settings </a-menu-item>
          <a-menu-divider />
          <a-menu-item key="3">
            <div>Logout</div>
          </a-menu-item>
        </a-menu>
      </template>
    </a-dropdown>
  </a-layout-header>
</template>
