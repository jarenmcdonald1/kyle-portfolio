<template>
  <div class="main text-center flex flex-col items-center justify-start">

    <div class="mb-4 w-full text-left">
      <h1 class="text-4xl md:text-3xl font-bold text-gray-800 dark:text-primary-300">Contact</h1>
      <div class="w-full bg-accent-400 dark:bg-accent-500 rounded-lg mt-2" style="height:2px;"></div>
    </div>
    
    <div class="w-auto sm:w-full max-w-lg pt-8">

      <div class="bg-gray-300 dark:bg-gray-800 rounded py-4 px-2 sm:px-4 md:px-6 md:py-6">

        <h2 class="text-6xl font-black tracking-tighter mb-4 text-accent-500">Say Hello</h2>

        <div class="mx-auto w-40 bg-gray-400 dark:bg-gray-700 mb-4 md:mb-6 rounded" style="height:1px;"></div>

        <div class="text-center">
          <h5 class="text-current mb-2 md:mb-4 md:text-lg"><a class="text-gray-800 dark:text-gray-400" href="tel:+19055551234">+1 (905) 555-1234</a></h5>
          <h5 class="text-current md:text-lg"><a class="text-gray-800 dark:text-gray-400" href="mailto:email@email.com">email@email.com</a></h5>
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
