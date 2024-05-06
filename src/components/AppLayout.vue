<template lang="">
  <div class="min-h-full bg-gray-200 flex">
    <!-- Sidebar -->
    <Sidebar :class="{'-ml-[200px]': !sidebarOpened}" />

    <div class="flex-1">
      <Navbar @toggle-sidebar="toggleSidebar" />

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
import { ref, onMounted, onUnmounted } from 'vue'
import Sidebar from './Sidebar.vue';
import Navbar from './Navbar.vue';

const { title } = defineProps({
  title: String,
});

const sidebarOpened = ref(true);

function toggleSidebar() {
  console.log("teste");
  sidebarOpened.value = !sidebarOpened.value;
}

onMounted(() => {
  handleSidebarUpdate();
  window.addEventListener('resize', handleSidebarUpdate)
});

onUnmounted(() => {
  window.removeEventListener('resize', handleSidebarUpdate)
});

function handleSidebarUpdate() {
  // if (window.outerWidth <= 768) {
  //   sidebarOpened.value = false;
  // } else {
  //   sidebarOpened.value = true;
  // }
  sidebarOpened.value = window.outerWidth > 768;
}
</script>

<style scoped></style>
