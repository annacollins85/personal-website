<template>
  <header class="navbar">
    <div
      v-for="link in links"
      :key="link.text"
      class="navbar__link"
      :class="currentPath === link.to && 'navbar__link--current'"
    >
      <a v-if="link.href" :href="link.href" target="_blank">
        {{ link.text }}
      </a>
      <nuxt-link v-else :to="link.to">
        {{ link.text }}
      </nuxt-link>
    </div>
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
          to: '/speaking',
          text: 'Speaking',
        },
        {
          href:
            'https://www.notion.so/GraphQL-101-62cba1b6ab744b838e1225a3f1f551e2',
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
  display: flex;
  justify-content: flex-end;
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
    a {
      text-decoration: none;
      color: black;
      border-bottom: 2px solid transparent;
      transition: border-bottom 0.3s;
    }
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
