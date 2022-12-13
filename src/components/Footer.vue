<template>
  <footer class="bg-blue-600">
    <section class="container px-4 py-6 text-center">
      <h4 class="pb-2 text-lg font-bold text-white">shortenIt</h4>
      <nav class="text-white">
        <ul class="flex items-center justify-center space-x-5">
          <li v-for="link in links">
            <a :href="link.url" class="text-sm hover:underline" target="_blank">{{ link.title }}</a>
          </li>
        </ul>
      </nav>
    </section>
  </footer>
</template>

<script setup>
import { ref } from "vue";

const links = ref([
  {
    title: "GitHub",
    url: "https://github.com/jmartindg/shortenIt",
  },
  {
    title: "API",
    url: "https://shrtco.de/",
  },
]);
</script>
