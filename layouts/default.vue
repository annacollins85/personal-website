<template>
  <div class="default">
    <NavBar />
    <Nuxt :key="$route.fullPath" />
    <Footer v-if="currentPath !== '/contact'" />
  </div>
</template>

<script>
import NavBar from '~/components/common/NavBar'
import Footer from '~/components/common/Footer'

export default {
  components: {
    NavBar,
    Footer,
  },
  computed: {
    currentPath() {
      return this.$route.path
    },
  },
}
</script>

<style lang="scss" scoped>
.default {
  position: relative;
}
</style>
