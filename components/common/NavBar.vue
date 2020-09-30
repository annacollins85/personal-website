<template>
  <header class="navbar">
    <nuxt-link
      v-for="link in links"
      :key="link.to"
      :to="link.to"
      class="navbar__link"
      :class="currentPath === link.to && 'navbar__link--current'"
    >
      {{ link.text }}
    </nuxt-link>
  </header>
</template>

<script>
export default {
  data() {
    return {
      links: [
        {
          to: '/',
          text: 'About Me',
        },
        {
          to: '/posts',
          text: 'Posts',
        },
        {
          to: '/graphql-workshop',
          text: 'GraphQL Workshop',
        },
        {
          to: '/contact',
          text: 'Contact',
        },
      ],
    }
  },
  computed: {
    currentPath() {
      return this.$route.path
    },
  },
}
</script>

<style lang="scss" scoped>
.navbar {
  position: absolute;
  top: 0;
  left: 0;
  padding: 48px;
  width: 100%;
  text-align: right;
  z-index: 1;
  &__link {
    margin-right: 24px;
    color: black;
    font-size: 16px;
    font-family: 'Merriweather', sans-serif;
    font-weight: 500;
    text-decoration: none;
    border-bottom: 2px solid transparent;
    transition: border-bottom 0.3s;
    &:last-child {
      margin-right: 0;
    }
    &:hover {
      border-bottom: 2px solid black;
    }
    &--current {
      border-bottom: 2px solid black;
    }
  }
}
</style>
