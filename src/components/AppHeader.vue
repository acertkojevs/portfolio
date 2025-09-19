<script setup lang="ts">
import { ref, onMounted, watch } from 'vue';
import { RouterLink } from 'vue-router';

// Mobile menu state
const isMobileMenuOpen = ref(false);
const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value;
};

// Theme state
const theme = ref('light');

// Load saved theme from localStorage
onMounted(() => {
  const savedTheme = localStorage.getItem('theme');
  if (savedTheme) theme.value = savedTheme;
  document.documentElement.setAttribute('data-theme', theme.value);
});

// Watch theme changes and save
watch(theme, (newTheme) => {
  document.documentElement.setAttribute('data-theme', newTheme);
  localStorage.setItem('theme', newTheme);
});
</script>

<template>
  <header class="fixed w-full z-50 bg-base-100 shadow-md">
    <nav class="w-[90%] md:w-[80%] mx-auto flex justify-between items-center py-3 relative">

      <!-- Desktop Menu -->
      <ul class="hidden md:flex flex-row gap-8">
        <RouterLink to="/" class="hover:text-amber-500">Home</RouterLink>
        <RouterLink to="/projects" class="hover:text-amber-500">Projects</RouterLink>
        <RouterLink to="/contact" class="hover:text-amber-500">Contact</RouterLink>
      </ul>

      <!-- Right side container for theme toggle + hamburger -->
      <div class="flex items-center w-full md:w-auto">
        <!-- Theme Toggle -->
        <label class="flex items-center gap-2 cursor-pointer">
          <!-- Sun icon -->
          <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-yellow-400" fill="none" stroke="currentColor"
            stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <circle cx="12" cy="12" r="5" />
            <path
              d="M12 1v2M12 21v2M4.2 4.2l1.4 1.4M18.4 18.4l1.4 1.4M1 12h2M21 12h2M4.2 19.8l1.4-1.4M18.4 5.6l1.4-1.4" />
          </svg>

          <input type="checkbox" class="toggle theme-controller" :checked="theme === 'dark'"
            @change="theme = ($event.target as HTMLInputElement).checked ? 'dark' : 'light'" />


          <!-- Moon icon -->
          <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-blue-600" fill="none" stroke="currentColor"
            stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"></path>
          </svg>
        </label>

        <!-- Mobile Hamburger (push to right with ml-auto) -->
        <button class="md:hidden ml-auto p-2 cursor-pointer" @click="toggleMobileMenu">
          <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"
            stroke-width="2">
            <path stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16M4 18h16" />
          </svg>
        </button>
      </div>

      <!-- Mobile Menu -->
      <div v-if="isMobileMenuOpen" class="absolute top-full left-0 w-full bg-base-100 shadow-md md:hidden ">
        <ul class="flex flex-col gap-4 p-4">
          <RouterLink to="/" class="hover:text-amber-500" @click="isMobileMenuOpen = false">Home</RouterLink>
          <RouterLink to="/projects" class="hover:text-amber-500" @click="isMobileMenuOpen = false">Projects
          </RouterLink>
          <RouterLink to="/contact" class="hover:text-amber-500" @click="isMobileMenuOpen = false">Contact</RouterLink>
        </ul>
      </div>

    </nav>
  </header>
</template>
