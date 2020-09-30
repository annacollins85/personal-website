<template>
  <slice-zone type="posts" uid="posts-list" class="posts" />
</template>

<script>
import SliceZone from 'vue-slicezone'

export default {
  components: {
    SliceZone,
  },
}
</script>

<style lang="scss" scoped>
.posts,
div > div {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
}
</style>
