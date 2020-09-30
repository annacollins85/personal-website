<template>
  <div class="default">
    <NavBar />
    <Nuxt />
  </div>
</template>

<script>
import NavBar from '~/components/common/NavBar'

export default {
  components: {
    NavBar,
  },
}
</script>

<style lang="scss" scoped>
.default {
  position: relative;
}
</style>
