<template>
  <header class="flex flex-wrap items-center px-2 py-2 lg-py-0 bg-white dark:bg-transparent">

    <div class="flex-1 flex justify-between items-center">
      <nuxt-link to="/" class="block font-normal">
        <span class="text-5xl md:text-4xl text-gray-800 dark:text-accent-500 font-light tracking-tighter"><span class="font-black">K</span>H</span>
      </nuxt-link>
    </div>

    <label for="menu-toggle" class="cursor-pointer block md:hidden p-2 bg-transparent hover:bg-gray-300 rounded text-gray-600 dark:text-gray-400">
      <svg class="fill-current text-current w-5 h-5" xmlns="https://www.w3.org/2000/svg" viewBox="0 0 20 20"><title>menu</title><path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z"></path></svg>
    </label>

    <input type="checkbox" class="hidden" id="menu-toggle" />

    <div class="hidden md:flex md:items-center w-full md:w-auto" id="menu">
      <nav>
        <ul class="flex flex-col md:flex-row items-center justify-between pt-4 md:pt-0">
          <li>
            <nuxt-link class="menu-btn" to="/about">About</nuxt-link>
          </li>
          <li>
            <nuxt-link class="menu-btn" to="/projects">Projects</nuxt-link>
          </li>
          <li class='hidden'>
            <nuxt-link class="menu-btn" to="/blog">Blog</nuxt-link>
          </li>
          <li>
            <nuxt-link class="menu-btn" to="/contact">Contact</nuxt-link>
          </li>
        </ul>
      </nav>
    </div>


    <!--<nav class="hidden">
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
    </nav>-->
  </header>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style lang="postcss" scoped>

  #menu-toggle:checked + #menu {
    display: block;
  }

.menu-btn {
  @apply py-4 px-6 block rounded border-b-2 border-transparent text-gray-400 text-2xl;
  &:hover {
    @apply bg-gray-800 text-accent-500;
  }
}
.nuxt-link-exact-active {
  @apply cursor-default block rounded border-b-2 border-transparent text-accent-500;
  &:hover {
    @apply bg-transparent;
  }
}

.light-mode {
  & .menu-btn {
    @apply text-gray-600;
    &:hover {
      @apply bg-gray-200 text-accent-500;
    }
  }
  & .nuxt-link-exact-active {
    @apply text-accent-500;
    &:hover {
      @apply bg-transparent;
    }
  }
}

@screen md {
  .menu-btn {
    @apply py-2 px-2 mx-3 block rounded border-b-2 border-transparent text-gray-400 text-base;
    &:hover {
      @apply bg-gray-800 text-accent-500;
    }
  }
  .nuxt-link-exact-active {
    @apply block rounded border-b-2 border-transparent text-accent-500;
    &:hover {
      @apply bg-transparent;
    }
  }

  .light-mode {
    & .menu-btn {
      @apply text-gray-600;
      &:hover {
        @apply bg-gray-200 text-accent-500;
      }
    }
    & .nuxt-link-exact-active {
      @apply text-accent-500;
      &:hover {
        @apply bg-transparent;
      }
    }
  }
}
</style>
