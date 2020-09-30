<template>
  <div class="posts">
    <slice-zone type="posts" uid="posts" />
  </div>
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
.posts {
  position: relative;
  z-index: -1;
  padding: 121px 56px 0;
}
</style>
