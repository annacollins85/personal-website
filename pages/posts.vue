<template>
  <div>
    <NavBar />
    POSTS
  </div>
</template>

<script>
import NavBar from '~/components/common/NavBar'

export default {
  components: {
    NavBar,
  },
  // mounted() {
  //   this.$nextTick(() => {
  //     this.$emit('pageLoaded')
  //   })
  // },
}
</script>

<style lang="scss" scoped>
.posts {
  max-width: 812px;
  margin: 0 auto;
}
</style>
