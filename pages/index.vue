<template>
  <div class="text-center flex flex-col items-center justify-center">

    <div class="grid grid-cols-1 grid-rows-1 justify-center items-center">

      <div class="col-span-1 row-span-1 row-start-1 col-start-1 h-full w-full overflow-hidden" style="max-height:600px;">
        <nuxt-img src="/img/laptop-pexels.jpg" class="banner-img" />
      </div>

      <div class="col-span-1 row-span-1 row-start-1 col-start-1"> 
        <div class="">
          <h1 class="title"><span class="font-black">Kyle</span> <span class="font-light">Hooper</span></h1>
          <h2 class="subtitle">Digital Content Creator</h2>
          <nuxt-link to="/about" class="btn">About Me ></nuxt-link>
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
  .banner-img {
    @apply object-cover object-center w-full h-full;
    min-height: 400px;
  }

  .title {
    @apply mb-2 text-gray-300 tracking-tight uppercase;
  }
  .subtitle {
    @apply mb-2 text-xl text-gray-400 uppercase;
  }

  .btn {
    @apply rounded-3xl text-lg bg-gray-500 bg-opacity-75 text-gray-200 shadow-md;

    &:hover {
      @apply bg-accent-500 shadow-2xl;
    }
  }
</style>
