<template>
  <main
    v-if="projectPosts"
    class="main"
  >
    <div class="mb-4 w-full text-left">
      <h1 class="text-4xl md:text-3xl font-bold text-gray-800 dark:text-primary-300">Projects</h1>
      <div class="w-full bg-accent-400 dark:bg-accent-500 rounded-lg mt-2" style="height:2px;"></div>
    </div>

    <ul
      v-for="(projectPost, index) in projectPosts"
      :key="index"
      class="articles"
    >
      <nuxt-link
        class="article article--clickable"
        :to="`projects/${projectPost.slug}`"
      >
        <h3 class="article-title">{{ projectPost.title }}</h3>
        <div class="mt-4 mb-2">
          <h2 class="inline py-1 px-2 mr-1 bg-accent text-white font-medium rounded-sm dark:bg-accent">{{ projectPost.project_type }}</h2>
          <p class="inline">{{ projectPost.description }}</p>
        </div>
      </nuxt-link>
    </ul>
  </main>
</template>

<script>
export default {
  computed: {
    projectPosts() {
      return this.$store.state.projectPosts
    }
  }
}
</script>
