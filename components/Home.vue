<template>
  <div class="bg-gray-900">
    <div class="">
      <header
        class="text-gray-100 flex flex-col"
        style="height: calc(100vh - 90px)"
      >
        <img
          src="/img/cover1.jpeg"
          class="w-full h-2/4 md:h-3/4 pt-6 object-cover absolute inline-block"
          alt=""
        />
        <div
          class="relative md:mt-auto ml-4 mt-24 text-center md:text-left lg:text-left md:ml-20 lg:ml-40"
        >
          <h1
            class="font-light font-serif italic text-gray-200 header-h text-4xl md:text-5xl lg:text-6xl pt-72"
          >
            Celtic Irish Music for the ages
          </h1>
          <br />
          <div class="header-t text-xl lg:text-2xl font-thin italic">
            Welcome to the experience...
          </div>
        </div>
        <div class="mx-auto pt-10">
          <a v-smooth-scroll="{ offset: -180 }" href="#welcome">
            <IconChevronRight
              class="h-16 w-16 text-gray-100 fill-current transition-opacity duration-700 transform rotate-90 text-center"
            />
          </a>
        </div>
      </header>
    </div>
    <!-- <div class="mx-auto px-6 md:px-10 lg:px-36"> -->
    <div class="w-screen py-6 px-6 md:px-10 lg:px-18 xl:px-24 bg-gray-100">
      <nuxt-content
        id="welcome"
        class="rounded-xl bg-gray-100 z-10 prose-2xl max-w-none md:px-14 lg:px-30 xl:px-40"
        :document="page"
      ></nuxt-content>
    </div>
    <!-- meet the band -->/
    <TheBand />
    <div>
      <div class="pb-8"></div>
    </div>
  </div>
</template>

<script>
import IconChevronRight from '@/assets/icons/chevron-right.svg?inline'

export default {
  components: { IconChevronRight },
  props: {
    page: {
      type: Object,
      default: null,
    },
  },
  data: () => {
    return {
      scrollY: 0,
      yTrigger: 20,
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

<style lang="stylus" scoped>
.header-t, .header-h {
  text-shadow: 2px 8px 6px rgba(0, 0, 0, 0.2), 0 -5px 35px rgba(255, 255, 255, 0.3), 0 4px 3px rgba(0, 0, 0, 0.4), 0 8px 13px rgba(0, 0, 0, 0.1), 0 18px 23px rgba(0, 0, 0, 0.1);
}

.header-t {
  text-shadow: 2px 2px 3px rgba(0, 0, 0, 0.3);
}
</style>
