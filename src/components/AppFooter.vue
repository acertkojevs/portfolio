<script lang="ts" setup>
import { Icon } from "@iconify/vue";
import { RouterLink } from "vue-router";
import { ref } from "vue";

const currentYear = ref(new Date().getFullYear());
</script>

<template>
  <footer class="transition-colors duration-300 border-t shadow-[0_-2px_10px_rgba(0,0,0,0.15)]
           bg-base-900 text-base-content">
    <div class="max-w-4xl mx-auto flex flex-col items-center space-y-4 py-6 px-4">

      <!-- Title -->
      <h6 class="text-lg font-semibold tracking-wide text-amber-500">
        Let’s Connect!
      </h6>

      <!-- Social Links -->
      <div class="flex justify-center gap-6">
        <RouterLink to="https://github.com/acertkojevs" target="_blank">
          <Icon icon="mdi:github" width="28" height="28"
            class="hover:text-primary transition-transform duration-300 hover:scale-110" />
        </RouterLink>
        <RouterLink to="https://www.linkedin.com/in/alans-%C4%8Dertkojevs-394ab7245/" target="_blank">
          <Icon icon="mdi:linkedin" width="28" height="28"
            class="hover:text-primary transition-transform duration-300 hover:scale-110" />
        </RouterLink>
      </div>

      <!-- Copyright -->
      <p class="text-sm opacity-70">
        © {{ currentYear }} acertojevs. All rights reserved.
      </p>
    </div>
  </footer>
</template>
