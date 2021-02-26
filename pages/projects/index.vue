<template>
  <main
    v-if="projectPosts"
    class="main"
  >
    <div class="mb-4 w-full text-left pt-2 md:pt-4">
      <h1 class="text-4xl md:text-3xl font-bold text-gray-800 dark:text-primary-300">Projects</h1>
      <div class="w-full bg-accent-400 dark:bg-accent-500 rounded-lg mt-2" style="height:2px;"></div>
    </div>

    <div
      v-for="(projectPost, index) in projectPosts"
      :key="index"
      class="project-articles"
      >

      <nuxt-link
        class="project-articles-item"
        :to="`projects/${projectPost.slug}`"
      >
        <div class="mb-2 sm:mb-3 md:mb-4 flex items-center">
          <h2 class="project-articles-type">{{ projectPost.project_type }}</h2>
          <h3 class="project-articles-title">{{ projectPost.title }}</h3>
        </div>
        <div>
          <p class="project-articles-date">{{new Date( projectPost.date ).toLocaleString('default', {month:'short'}) }} {{ new Date( projectPost.date ).getDate() }}, {{ new Date( projectPost.date ).getFullYear() }}</p>
          <p class="project-articles-text">{{ projectPost.description }}</p>
        </div>
      </nuxt-link> 

    </div>

    <ul
      v-for="(projectPost, index) in projectPosts"
      :key="index"
      class="hidden articles"
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

<style lang="postcss" scoped>
  .project-articles {
    @apply flex flex-col pt-2;
  }

  .project-articles-item {
    @apply mb-4 py-3 px-4 bg-transparent rounded-lg text-gray-300 transition;
    &:hover {
      @apply text-accent-400 bg-primary-800;
    }
  }

  .project-articles-type {
    @apply mr-2 py-3 px-2 text-sm text-gray-300 bg-accent-600 uppercase rounded;
  }

  .project-articles-title {
    @apply text-2xl text-current capitalize;
  }

  .project-articles-date {
    @apply mb-1 text-gray-600;
  }

  .project-articles-text {
    @apply text-gray-300 font-normal leading-tight;
  }

  .light-mode {
    & .project-articles-item {
      @apply text-gray-800 shadow-md bg-white;
      &:hover {
        @apply text-accent-500 shadow-2xl bg-white;
      }
    }
    & .project-articles-type {
      @apply text-gray-100 bg-accent-500;
    }
    & .project-articles-text {
      @apply text-gray-800;
    }
  }

  @screen md {
    .project-articles {
      @apply pt-6;
    }
    .project-articles-item {
      @apply mb-8 py-4 px-6 rounded-md;
    }
    .project-articles-title {
      @apply text-3xl;
    }
  }
</style>
