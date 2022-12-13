<template>
  <section class="min-h-max bg-blue-500 px-4 pt-10 pb-16 text-center">
    <h1 class="text-4xl font-bold text-white lg:text-5xl">shortenIt</h1>
    <p class="mx-auto pt-5 pb-7 text-white md:w-8/12 md:text-lg lg:w-1/2">
      shortenIt is a free tool to shorten a URL or reduce a link. Create a short link with our URL shortener to make it
      simple to remember.
    </p>

    <form class="flex flex-col justify-center md:flex-row">
      <input
        type="url"
        class="mb-2 h-10 w-full border-2 border-gray-200 px-4 focus:border-blue-500 focus:outline-none md:mb-0 md:h-12 md:w-1/2 md:rounded-l-md"
        placeholder="Paste your link here"
      />
      <input
        type="submit"
        value="Shorten"
        class="h-10 w-full cursor-pointer bg-blue-700 text-white transition duration-300 ease-in-out hover:bg-blue-800 md:h-12 md:w-1/6 md:rounded-r-md"
      />
    </form>
  </section>
</template>

<script setup></script>
