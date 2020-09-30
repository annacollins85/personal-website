<template>
  <a v-scroll-to="`#${element}`" href="#" class="scroll-to">⌄</a>
</template>

<script>
export default {
  props: {
    element: {
      type: String,
      required: true,
    },
  },
}
</script>

<style lang="scss" scoped>
.scroll-to {
  text-align: center;
  text-decoration: none;
  font-size: 36px;
  padding-bottom: 0.25rem;
  color: black;
}
</style>
