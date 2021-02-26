<template>
  <div class="main text-center flex flex-col items-center justify-start">

    <div class="mb-4 w-full text-left pt-2 md:pt-4">
      <h1 class="text-4xl md:text-3xl font-bold text-gray-800 dark:text-primary-300">Contact</h1>
      <div class="w-full bg-accent-400 dark:bg-accent-500 rounded-lg mt-2" style="height:2px;"></div>
    </div>
    
    <div class="w-auto sm:w-full max-w-lg pt-8 md:pt-10">

      <div class="bg-gray-300 dark:bg-gray-800 rounded py-4 sm:py-6 px-2 sm:px-4 md:px-6 md:py-6">

        <h2 class="text-6xl font-black tracking-tighter mb-4 text-accent-500">Say Hello</h2>

        <div class="mx-auto w-40 bg-gray-400 dark:bg-gray-700 mb-4 md:mb-6 rounded" style="height:1px;"></div>

        <div class="flex flex-col md:flex-row justify-center items-center">
          <a class="hidden btn contact-btn" href="tel:+19055551234">+1 (905) 555-1234</a>
          <a class="btn contact-btn" href="mailto:kyhooper5@gmail.com">kyhooper5@gmail.com</a>
        </div>

      </div>

    </div>

  </div>

</template>

<script>
export default {
  head() {
    return {
      script: [{ src: 'https://identity.netlify.com/v1/netlify-identity-widget.js' }]
    }
  }
}
</script>

<style lang="postcss" scoped>
  .contact-btn {
    @apply mb-2 text-gray-400 text-lg bg-gray-700 bg-opacity-75 rounded-2xl;
    &:hover {
      @apply bg-accent-600 bg-opacity-100;
    }
  }

  .light-mode {
    & .contact-btn {
      @apply text-gray-100 bg-gray-500 shadow-md transition;

      &:hover {
        @apply shadow-lg bg-accent-500;
      }
    }
  }

  @screen md {
    .contact-btn {
      @apply mx-2;
    }
  }
</style>
