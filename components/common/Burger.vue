<template>
  <div class="burger">
    <div v-if="open">&#10005;</div>
    <div v-else>🍔</div>
  </div>
</template>

<script>
export default {
  props: {
    open: {
      type: Boolean,
      required: true,
    },
  },
}
</script>

<style lang="scss" scoped>
.burger {
  font-size: 32px;
}
</style>
