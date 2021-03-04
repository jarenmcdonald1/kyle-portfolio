<template>

  <article
    v-if="projectPost"
    class="main article main-article mb-2 md:mb-4 pt-4 md:pt-6"
  >
    <h1 class="article-title">{{ projectPost.title }}</h1>
    <p class="article-date">{{new Date( projectPost.date ).toLocaleString('default', {month:'long'}) }} {{ new Date( projectPost.date ).getDate() }}, {{ new Date( projectPost.date ).getFullYear() }}</p>
    <nuxt-img
      class="cover-image w-full"
      :src="projectPost.cover"
    />

    <div v-if="projectPost.videoLink">
      <div class="embed-r-con">
        <iframe class="embed-r-item mx-auto" :src="`https://www.youtube.com/embed/${projectPost.videoLink}`"
            frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope;
            picture-in-picture" allowfullscreen
        >
        </iframe>
      </div>
    </div>

    <div v-if="projectPost.link">
      <div class="flex justify-center w-full py-4 md:py-6">
        <a :href="`${projectPost.link}`" class="btn project-link-btn">View more</a>
      </div>
    </div>

    <div
      class="block mt-8 mb-4 article-body"
      v-html="$md.render(projectPost.body)"
    ></div> 

    <div v-if="projectPost.gallery" class="flex flex-col justify-center items-center">
      <nuxt-img
        v-for="image in projectPost.gallery"
        class="image mb-4 mx-auto"
        :key="image.id"
        :src="image"
        style="width:100%;max-width:800px;"
        loading="lazy"
      />
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

  /*.embed-r-con {
    position: relative;
    overflow: hidden;
    width: 100%;
    height: auto;
  }
  .embed-r-item::after {
    display: block;
    content: "";
    padding-top: 56.25%.
  }
  .embed-r-con >>> iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }*/

  .article-title {
    @apply mb-2 text-4xl text-gray-300;
  }

  .article-date {
    @apply text-sm font-bold text-gray-600;
  }

  .article-body {
    @apply text-gray-300 font-sans font-medium leading-5;
  }

  .project-link-btn {
    @apply py-4 px-4 text-lg bg-gray-800 text-accent-500;

    &:hover {
      @apply text-gray-300 bg-accent-600;
    }
  }

  .light-mode {
    & .article-title {
      @apply text-gray-800;
    }
    & .article-body {
      @apply text-gray-800;
    }
    & .project-link-btn {
      @apply text-gray-200 bg-gray-600 bg-opacity-75 shadow-md;
      &:hover {
        @apply text-gray-100 bg-accent-500 bg-opacity-100 shadow-xl;
      }
    }
  }

  @screen md {
    .article-title {
      @apply text-5xl;
    }

    .project-link-btn {
      @apply text-xl;
    }
  }

</style>
