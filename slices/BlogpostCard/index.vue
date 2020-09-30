<template>
  <a :href="slice.primary.url" class="blogpost-card">
    <prismic-rich-text
      :field="slice.primary.title"
      class="blogpost-card__title"
    />
    <div>{{ slice.primary.published_date }}</div>
    <prismic-rich-text
      :field="slice.primary.description"
      class="blogpost-card__description"
    />
  </a>
</template>

<script>
export default {
  props: {
    slice: {
      type: Object,
      required: true,
    },
  },
  computed: {
    url() {
      return this.slice.primary.url?.url || '#'
    },
  },
}
</script>
<style lang="scss" scoped>
.blogpost-card {
  display: flex;
  flex-direction: column;
  color: black;
  text-decoration: none;
  margin-top: 36px;
  &__title {
    font-family: 'Merriweather', serif;
  }
}
</style>
