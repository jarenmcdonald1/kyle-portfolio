<template>
  <div class="flex flex-col justify-center items-center">

    <footer class="w-full flex flex-wrap items-center px-2 md:px-4 py-2 sm:py-6 bg-gray-700 dark:bg-primary-800">

        <div class="flex flex-col md:flex-row md:items-center w-full md:justify-center">
            <nav>
                <ul class="flex flex-col sm:flex-row items-center justify-around pt-4 md:pt-0">
                <li>
                    <nuxt-link class="menu-btn" to="/about">About</nuxt-link>
                </li>
                <li>
                    <nuxt-link class="menu-btn" to="/projects">Projects</nuxt-link>
                </li>
                <li class="hidden">
                    <nuxt-link class="menu-btn" to="/blog">Blog</nuxt-link>
                </li>
                <li>
                    <nuxt-link class="menu-btn" to="/contact">Contact</nuxt-link>
                </li>
                </ul>
            </nav>
        </div>

        <div class="hidden items-center justify-around w-full">
            <a class="social-icons-btn" href="#">
                <span class="sr-only">Twitter</span>
            </a>
        </div>

    </footer>

    <div class="copyright flex flex-col sm:flex-row items-center justify-center bg-gray-800 dark:bg-primary-800 py-4 px-2 text-center w-full">
        <p class="text-sm text-gray-600 mb-2 sm:mb-0 sm:mr-1">Copyright <span class="copy-year">{{new Date().getFullYear()}}</span></p>
        <p class="text-sm text-gray-600">By <a class="text-current hover:text-accent-500" href="https://jaren.ca">Jaren McDonald</a></p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Footer'
}
</script>

<style lang="postcss" scoped>

.menu-btn {
  @apply py-4 px-6 block rounded border-b-2 border-transparent text-gray-600 text-xl;
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
    @apply text-gray-400;
    &:hover {
      @apply bg-gray-600 text-gray-100;
    }
  }
  & .nuxt-link-exact-active {
    @apply text-accent-500;
    &:hover {
      @apply bg-transparent text-accent-500;
    }
  }
}

@screen md {
  .menu-btn {
    @apply py-2 px-2 block rounded border-b-2 border-transparent text-gray-600 text-base;
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
        @apply text-gray-400;
        &:hover {
        @apply bg-gray-600 text-gray-100;
        }
    }
    & .nuxt-link-exact-active {
        @apply text-accent-500;
        &:hover {
        @apply bg-transparent text-accent-500;
        }
    }
  }
}
</style>
