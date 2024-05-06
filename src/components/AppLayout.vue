<template lang="">
  <div class="min-h-full flex">
    <!-- Sidebar -->
    <Sidebar />

    <div>
      <header class="h-8 shadow bg-white">Header</header>

      <!-- Content -->
      <main>
        <router-view></router-view>
      </main>
    </div>
  </div>
</template>

<script setup>
import Sidebar from './Sidebar.vue';

const { title } = defineProps({
  title: String,
});
</script>

<style scoped></style>
