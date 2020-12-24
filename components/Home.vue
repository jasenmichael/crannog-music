<template>
  <div>
    <!-- <header class="h-full text-gray-100 flex flex-col">
      <h1 class="font-thin text-4xl mt-auto pt-18">
        Welcome to the experience...
      </h1>
      <div class="ml-auto mt-auto px-10 pb-10">
        Facebook Twitter Instagram Email
      </div>
    </header> -->
    <nuxt-content :document="page"></nuxt-content>
  </div>
</template>

<script>
export default {
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
