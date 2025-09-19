<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';

const messages = [
  { text: "Connect", class: "bg-red-500" },
  { text: "Collaborate", class: "bg-green-500" },
  { text: "Create", class: "bg-blue-500" }
];

const index = ref(0);
const intervalId = ref<number | null>(null);

onMounted(() => {
  intervalId.value = setInterval(() => {
    index.value = (index.value + 1) % messages.length;
  }, 2500);
});

onUnmounted(() => {
  if (intervalId.value !== null) clearInterval(intervalId.value);
});
</script>

<template>
  <section class="flex flex-col items-center justify-center py-20 px-4 min-h-screen bg-base-200">

    <!-- Hero Text -->
    <div class="flex flex-col items-center gap-2 text-center mb-6">
      <h1 class="text-4xl sm:text-5xl font-bold text-base-content">
        Let's
      </h1>

      <!-- Animated message -->
      <h1 v-for="(msg, i) in messages" v-show="i === index" :key="msg.text"
        class="px-6 py-2 rounded-xl font-bold text-white text-4xl sm:text-5xl shadow-lg" :class="msg.class">
        {{ msg.text }}
      </h1>

      <h1 class="text-4xl sm:text-5xl font-bold text-base-content">
        Together!
      </h1>
    </div>

    <!-- Contact Form -->
    <form class="flex flex-col gap-4 w-full max-w-md p-8 rounded-2xl shadow-xl border bg-base-100 border-base-300">

      <input type="text" placeholder="Your Name"
        class="input input-bordered w-full bg-base-200 text-base-content border-base-300 focus:border-amber-500" />

      <input type="email" placeholder="Your Email"
        class="input input-bordered w-full bg-base-200 text-base-content border-base-300 focus:border-amber-500" />

      <textarea placeholder="Your Message"
        class="textarea textarea-bordered w-full bg-base-200 text-base-content border-base-300 focus:border-amber-500"></textarea>

      <button type="submit"
        class="btn w-full btn-primary text-white font-bold transition-all duration-300 transform hover:scale-105">
        Send Message
      </button>
    </form>

  </section>
</template>
