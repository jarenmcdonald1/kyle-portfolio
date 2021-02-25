<template>

  <article
    v-if="projectPost"
    class="main article main-article mb-2 md:mb-4"
  >
    <h1 class="article-title">{{ projectPost.title }}</h1>
    <p class="article-date">{{new Date( projectPost.date ).toLocaleString('default', {month:'long'}) }} {{ new Date( projectPost.date ).getDate() }}, {{ new Date( projectPost.date ).getFullYear() }}</p>
    <img
      class="cover-image"
      :src="projectPost.cover"
    >

    <div v-if="projectPost.videoLink">
      <div class="embed-responsive aspect-ratio-16/9">
        <iframe class="embed-responsive-item" :src="`https://www.youtube.com/embed/${video}`"
            frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope;
            picture-in-picture" allowfullscreen
        >
        </iframe>
      </div>
    </div>

    <div
      class="block mt-8 mb-4 article-body"
      v-html="$md.render(projectPost.body)"
    />
    <div v-if="projectPost.gallery">
      <img
        v-for="image in projectPost.gallery"
        class="image"
        :key="image.id"
        :src="image"
      >
    </div>
  </article>

</template>

<script>
export default {
  async asyncData({ params, payload }) {
    if (payload) return { projectPost: payload }
    else
      return {
        projectPost: await require(`~/assets/content/projects/${params.project}.json`)
      }
  }
}
</script>

<style lang="postcss" scoped>

  .article-title {
    @apply mb-2 text-4xl text-gray-300;
  }

  .article-date {
    @apply text-sm font-bold text-gray-600;
  }

  .article-body {
    @apply text-gray-300;
  }

  .light-mode {
    & .article-title {
      @apply text-gray-800;
    }
    & .article-body {
      @apply text-gray-800;
    }
  }

  @screen md {
    .article-title {
      @apply text-5xl;
    }
  }

</style>
