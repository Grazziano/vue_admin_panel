<template lang="">
  <div class="min-h-full bg-gray-200 flex">
    <!-- Sidebar -->
    <Sidebar :class="{'-ml-[200px]': !sidebarOpened}" />

    <div class="flex-1">
      <TopHeader @toggle-sidebar="toggleSidebar" />

      <!-- Content -->
      <main class="p-6">
        <div class="p-4 rounded bg-white">
          <router-view></router-view>
        </div>
      </main>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import Sidebar from './Sidebar.vue';
import TopHeader from './TopHeader.vue';

const { title } = defineProps({
  title: String,
});

const sidebarOpened = ref(true);

function toggleSidebar() {
  console.log("teste");
  sidebarOpened.value = !sidebarOpened.value;
}
</script>

<style scoped></style>
