<template>
  <div class="workshop">
    <slice-zone type="workshop" uid="graphql-workshop" />
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
.workshop {
  position: relative;
  z-index: -1;
  padding: 121px 56px 0;
}
</style>
