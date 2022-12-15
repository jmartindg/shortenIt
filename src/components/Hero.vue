<template>
  <main class="min-h-max bg-blue-600 px-4 pt-10 pb-16 text-center">
    <section class="mx-auto max-w-4xl">
      <h1 class="text-4xl font-bold text-white lg:text-5xl">shortenIt</h1>
      <p class="mx-auto pt-5 pb-7 text-white md:w-2/3 md:text-lg">
        shortenIt is a free tool to shorten a URL or reduce a link. Create a short link with our URL shortener to make it
        simple to remember.
      </p>

      <form @submit.prevent="shortenUrl" class="md:grid md:grid-cols-12">
        <input v-model="urlInput" type="url" class="url-input" placeholder="Paste your link here" />
        <input type="submit" value="Shorten" class="submit-btn" />
      </form>

      <article v-if="loading" v-show="shortenedUrl">
        <Icon icon="line-md:loading-loop" color="white" class="mx-auto pt-10 text-8xl" />
      </article>
      <article
        v-if="shortenedUrl"
        v-show="!loading"
        class="mt-5 flex flex-col items-center justify-between rounded bg-white p-4 sm:flex-row"
      >
        <p class="mb-3 font-semibold sm:mb-0">{{ shortenedUrl }}</p>
        <button @click="copy(shortenedUrl)" class="copy-btn w-full sm:w-auto">
          <span v-if="!copied">Copy to Clipboard</span>
          <span v-else>Copied!</span>
        </button>
      </article>
    </section>
  </main>
</template>

<script setup>
import { Icon } from "@iconify/vue";
import { useClipboard } from "@vueuse/core";
import { ref } from "vue";

const urlInput = ref("");
const shortenedUrl = ref("");
const loading = ref(false);

const { copy, copied } = useClipboard({ text: shortenedUrl, legacy: true });

const shortenUrl = async () => {
  try {
    loading.value = true;
    const response = await fetch(`https://api.shrtco.de/v2/shorten?url=${urlInput.value}`);
    const data = await response.json();
    shortenedUrl.value = data.result.full_short_link;
    urlInput.value = "";
  } catch (error) {
    console.log(error);
    urlInput.value = "";
  } finally {
    loading.value = false;
  }
};
</script>
