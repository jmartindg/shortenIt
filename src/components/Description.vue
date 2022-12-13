<template>
  <section class="container px-4 py-16">
    <h2 class="rounded-l border-l-4 border-l-blue-600 pl-2 text-xl font-bold md:text-2xl">
      Simple, fast, and Secure URL shortener
    </h2>
    <p class="pt-3 text-sm leading-6 md:text-base md:leading-normal">
      A URL shortener is a tool that takes long, unwieldy URLs and condenses them into shorter, more manageable links. This
      is useful for a variety of reasons, including making it easier to share links on social media or in messaging apps, or
      to reduce the amount of space taken up by a link in a document or email. To use a URL shortener, you simply enter the
      long URL into the app or website, and it will generate a shortened version that you can copy and paste wherever you
      need it.
    </p>

    <section class="grid gap-10 py-10 md:grid-cols-2 lg:grid-cols-3">
      <article v-for="feature in features">
        <Icon :icon="feature.icon" class="text-4xl text-blue-600" />
        <h3 class="pt-2 text-lg font-semibold">{{ feature.title }}</h3>
        <p class="pt-1 text-sm">{{ feature.description }}</p>
      </article>
    </section>
  </section>
</template>

<script setup>
import { Icon } from "@iconify/vue";
import { ref } from "vue";

const features = ref([
  {
    icon: "ph:thumbs-up-bold",
    title: "Easy",
    description: "shortenIt is easy and fast to use, paste the long link to get your shortened link",
  },
  {
    icon: "mdi:encryption-secure-outline",
    title: "Secure",
    description: "shortenIt is more than just another URL Shortener, it is a powerful tool to protect your links",
  },
  {
    icon: "material-symbols:add-link",
    title: "Shortened",
    description: "Use any link, no matter what size, shortenIt always shortens",
  },
  {
    icon: "material-symbols:check-circle-outline",
    title: "Reliable",
    description: "All links that try to disseminate spam, viruses and malware are deleted",
  },
  {
    icon: "carbon:devices",
    title: "Devices",
    description: "Compatible with modern devices such as smartphones, tablets, and desktop",
  },
  {
    icon: "material-symbols:query-stats",
    title: "Statistics",
    description: "Check the amount of clicks that your shortened url received",
  },
]);
</script>
