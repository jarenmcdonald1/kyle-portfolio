<template>
  <div class="main text-center flex flex-col items-center justify-start">

    <div class="mb-4 pt-2 md:pt-4 w-full text-left">
      <h1 class="text-4xl md:text-3xl font-bold text-gray-800 dark:text-primary-300">About</h1>
      <div class="w-full bg-accent-400 dark:bg-accent-500 rounded-lg mt-2" style="height:2px;"></div>
    </div>
    
    <div class="w-full">
      
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

<style lang="postcss" scoped></style>
