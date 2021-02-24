<template>
  <main
    v-if="blogPosts"
    class="main"
  >

    <div class="mb-4 w-full text-left">
      <h1 class="text-4xl md:text-3xl font-bold text-gray-800 dark:text-primary-300">Blog Posts</h1>
      <div class="w-full bg-accent-400 dark:bg-accent-500 rounded-lg mt-2" style="height:2px;"></div>
    </div>

    <ul
      v-for="(blogPost, index) in blogPosts"
      :key="index"
      class="articles"
    >
      <nuxt-link
        :to="`blog/${blogPost.slug}`"
        class="article article--clickable"
      >
        <div class="flex justify-between align-baseline">
          <h3 class="article-title">{{ blogPost.title }}</h3>
          <h6
            v-if="blogPost.date"
            class="inline-block py-1 px-2 bg-accent text-white font-medium rounded-sm dark:bg-accent whitespace-no-wrap"
          >{{ formatDate(blogPost.date) }}</h6>
        </div>
        <div class="mt-4 mb-2">
          <p class="inline">{{ blogPost.description }}</p>
        </div>
      </nuxt-link>
    </ul>
  </main>
</template>
<script>
export default {
  computed: {
    blogPosts() {
      return this.$store.state.blogPosts
    }
  },
  methods: {
    formatDate(dateString) {
      const date = new Date(dateString)
      return date.toLocaleDateString(process.env.lang) || ''
    }
  }
}
</script>
