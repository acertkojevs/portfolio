<script setup lang="ts">
import { RouterLink } from 'vue-router';
</script>

<template>
  <!-- Page wrapper with theme-aware background -->
  <div class="bg-base-200 min-h-screen">

    <!-- Hero Section -->
    <section class="flex justify-center">
      <div class="w-[80%] flex flex-col md:flex-row justify-between items-center pt-20 pb-10 gap-10">

        <!-- Left: Intro text -->
        <div class="text-center md:text-left space-y-6 max-w-2xl">
          <h1 class="text-4xl md:text-5xl font-Sofia text-base-content">
            Hi 👋, I'm
            <span class="bg-clip-text text-transparent bg-gradient-to-r from-amber-400 to-yellow-500 font-bold">
              Alans Čertkojevs
            </span>
          </h1>

          <p class="text-base-content/70 text-lg italic">
            Learning WEB development & building projects!
          </p>

          <p class="text-base-content/70 text-lg leading-relaxed">
            I currently work in an operations role where I handle data, move files, and create bookings in internal
            systems. Along the way, I’ve been improving processes with small automations using Python and Google Apps
            Script.
          </p>

          <div class="flex justify-center md:justify-start gap-4 pt-4">
            <RouterLink to="/projects" class="btn btn-primary px-6 py-2 transition-all duration-300 hover:scale-105">
              View Projects
            </RouterLink>
            <RouterLink to="/contact"
              class="btn btn-outline btn-primary px-6 py-2 transition-all duration-300 hover:scale-105">
              Contact Me
            </RouterLink>
          </div>
        </div>

        <!-- Right: Image -->
        <div class="avatar py-10">
          <div
            class="w-64 rounded-full overflow-hidden shadow-2xl ring-2 ring-amber-500 hover:scale-105 transition-transform duration-500">
            <img src="../assets/portfolio.jpg" class="object-cover object-[0%_60%]" alt="Portfolio Photo" />
          </div>
        </div>

      </div>
    </section>

    <!-- About Me Section -->
    <section class="flex justify-center pb-20">
      <div class="w-[80%] bg-base-100 rounded-2xl shadow-xl p-10 border border-base-300">

        <h2 class="text-3xl font-playfair font-bold mb-4 pb-2 text-base-content border-b border-base-300">
          About Me
        </h2>

        <p class="text-base-content/70 mt-4 leading-relaxed text-lg py-2">
          I have a Bachelor's degree in Computer Management and Computer Science.
          My work experience has given me a solid foundation in working with data, creating reports, and keeping systems
          accurate.
        </p>

        <p class="text-base-content/70 mt-4 leading-relaxed text-lg py-2">
          I’m actively learning modern web development — focusing on Vue.js, Tailwind CSS, and Node.js — and I build
          personal projects to grow my skills with the goal of becoming a developer.
        </p>

        <ul class="list-disc text-base-content/70 pl-6 py-4 grid grid-cols-2 gap-3 text-sm">
          <li>SQL (PL/SQL, PostgreSQL, MySQL)</li>
          <li>Python, Google Apps Script</li>
          <li>Vue.js, Daisy UI</li>
          <li>Tailwind CSS, Bootstrap</li>
          <li>Git / GitHub / GitLab</li>
          <li>Data Handling & Process Automation</li>
        </ul>
      </div>
    </section>

  </div>
</template>
