<script setup lang="ts">
import { RouterView } from 'vue-router'
import AppFooter from './components/AppFooter.vue';
import AppHeader from './components/AppHeader.vue';
</script>

<template>
  <main class="min-h-screen flex flex-col">
    <AppHeader />
    <main class="grow">
      <router-view />
    </main>
    <AppFooter />
  </main>
</template>
