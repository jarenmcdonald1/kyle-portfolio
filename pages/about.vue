<template>
  <div class="main text-center flex flex-col items-center justify-start">

    <div class="mb-4 md:mb-8 pt-2 md:pt-4 w-full text-left">
      <h1 class="text-4xl md:text-3xl font-bold text-gray-800 dark:text-primary-300">About</h1>
      <div class="w-full bg-accent-400 dark:bg-accent-500 rounded-lg mt-2" style="height:2px;"></div>
    </div>
    
    <div class="w-full mx-auto text-left pt-4 md:pt-8" style="max-width:600px">
      <p class="mb-2">Hey, thanks for taking the time to look at my portfolio. My name is Kyle Hooper, and I'm a recent graduate of the Mohawk College journalism program. I wear many hats when it comes to journalism, from on-camera personality to behind-the-scenes editor. I enjoy new challenges and working with a team to accomplish goals.</p>
      <p>I am looking to leverage my excellent storytelling skills and experience to contribute to high-quality work. Technologically adept, offering experience with many social media platforms, office technology programs, and advanced computer skills. Behind all of this, I love getting out to play hockey and enjoy gaming in my spare time. I'm open, honest and not afraid to say I don't know how to do something.</p>
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
  
</style>
