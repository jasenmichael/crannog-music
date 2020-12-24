<template>
  <nav
    class="shadow text-gray-300"
    :class="
      scrollY >= yTrigger
        ? 'bg-gray-800 fixed w-screen z-10'
        : 'bg-gray-900 py-5'
    "
  >
    <div
      class="container mx-auto px-6 py-3 md:flex md:justify-between md:items-center"
    >
      <div class="flex justify-between items-center">
        <!-- brand -->
        <div>
          <nuxt-link
            class="text-gray-300 italic font-thin text-2xl md:text-3xl lg:text-4xl hover:text-gray-400"
            to="/"
          >
            {{ $config.siteData.name }}
          </nuxt-link>
        </div>

        <!-- mobile menu -->
        <div class="flex md:hidden" @click="menu = !menu">
          <div class="w-6 h-6 bg-white ml-14 rounded-md"></div>
        </div>
      </div>

      <!-- desktop links -->
      <div
        class="transition duration-500 ease-in-out md:flex items-center"
        :class="menu ? 'pt-2 block' : 'hidden'"
      >
        <div
          class="flex flex-col md:flex-row md:mx-6 space-y-1 md:space-x-6 md:space-y-0"
        >
          <nuxt-link
            v-for="(post, i) in $config.navigation.posts"
            :key="i"
            :to="post.path"
            class="text-sm md:text-base lg:text-lg text-gray-200 font-medium hover:text-indigo-500"
            >{{ post.title }}</nuxt-link
          >
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data: () => {
    return {
      scrollY: 0,
      yTrigger: 1,
      menu: false,
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll() {
      this.scrollY = window.scrollY
    },
  },
}
</script>
