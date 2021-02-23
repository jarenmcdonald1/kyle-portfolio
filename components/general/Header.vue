<template>
  <header>

    <nav class="flex fixed top-0 inset-x-0 p-3 justify-end">
      <div>
        <nuxt-link class="btn" to="/">Home</nuxt-link>
      </div>
      <div>
        <nuxt-link class="btn" to="/">About</nuxt-link>
      </div>
      <div>
        <nuxt-link class="btn" to="/projects">Projects</nuxt-link>
      </div>
      <div>
        <nuxt-link class="btn" to="/blog">Blog</nuxt-link>
      </div>
      <div>
        <nuxt-link class="btn" to="/">Contact</nuxt-link>
      </div>
    </nav>


    <nav class="hidden">
      <ul class="flex fixed top-0 inset-x-0 p-3">
        <li class="flex-1 mr-2">
          <nuxt-link class="btn block" to="/">Home</nuxt-link>
        </li>
        <li class="flex-1 mr-2">
          <nuxt-link class="btn block" to="/blog">Blog</nuxt-link>
        </li>
        <li class="flex-1">
          <nuxt-link class="btn block" to="/projects">Projects</nuxt-link>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style lang="postcss" scoped>
.nuxt-link-exact-active {
  @apply text-primary-300 bg-transparent bg-opacity-20;
  &:hover {
    @apply text-primary-300 bg-transparent;
  }
}
.light-mode {
  & .nuxt-link-exact-active {
    @apply text-primary-500;
    &:hover {
      @apply text-primary-500 bg-transparent;
    }
  }
}
</style>
