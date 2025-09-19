<script setup lang="ts">
import { RouterView } from 'vue-router'
import AppFooter from './components/AppFooter.vue';
import AppHeader from './components/AppHeader.vue';
</script>

<template>
  <div class="min-h-screen flex flex-col ">
    <AppHeader />

    <main class="flex-1">
      <router-view />
    </main>

    <AppFooter />
  </div>
</template>
