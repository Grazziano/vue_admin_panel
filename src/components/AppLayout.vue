<template lang="">
  <div class="min-h-full bg-gray-200 flex">
    <!-- Sidebar -->
    <Sidebar />

    <div class="flex-1">
      <TopHeader />

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
import Sidebar from './Sidebar.vue';
import TopHeader from './TopHeader.vue';

const { title } = defineProps({
  title: String,
});
</script>

<style scoped></style>
