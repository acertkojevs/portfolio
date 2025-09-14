<script lang="ts" setup>
import { Icon } from "@iconify/vue";
import { RouterLink } from "vue-router";

</script>

<template>
  <footer class="bg-gray-900 text-white py-6 px-4">
    <h6 class="text-center text-lg font-semibold mb-2 underline">Let's Connect!</h6>
    <p class="text-center text-sm pb-2">© 2025 acertojevs. All rights reserved.</p>
    <div class="flex justify-center gap-4">
      <RouterLink to="https://github.com/acertkojevs">
        <Icon icon="mdi:github" width="24" height="24" class="hover:text-gray-400 transition-colors" />
      </RouterLink>
      <router-link to="https://www.linkedin.com/in/alans-%C4%8Dertkojevs-394ab7245/">
        <Icon icon="mdi:linkedin" width="24" height="24" class="hover:text-blue-500 transition-colors" />
      </router-link>
    </div>
  </footer>
</template>
