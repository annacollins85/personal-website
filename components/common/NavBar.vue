<template>
  <div>
    <div v-show="isMenuVisible" class="overlay" />
    <header class="header" :class="scrolled && 'header--scrolled'">
      <div class="header__content">
        <div class="header__home" @click="closeMenu">
          <nuxt-link aria-label="link to homepage" to="/">
            🏠
          </nuxt-link>
        </div>
        <button class="header__toggle" @click="toggleMenu">
          <Burger :open="isMenuVisible" />
        </button>
        <nav :class="`menu ${isMenuVisible ? '' : 'menu--hidden'}`">
          <ul class="menu__links">
            <li
              v-for="link in links"
              :key="link.text"
              class="menu__link"
              :class="
                (currentPath === link.to || initialPath === link.to) &&
                'menu__link--current'
              "
              @click="closeMenu"
            >
              <a
                v-if="link.href"
                :href="link.href"
                target="_blank"
                rel="noopener"
              >
                {{ link.text }}
              </a>
              <nuxt-link v-else :to="link.to">
                {{ link.text }}
              </nuxt-link>
            </li>
          </ul>
        </nav>
      </div>
    </header>
  </div>
</template>

<script>
import throttle from 'lodash.throttle'
import Burger from '~/components/common/Burger'

export default {
  components: {
    Burger,
  },
  data() {
    return {
      scrolled: false,
      throttleHandleScroll: null,
      content: null,
      initialPath: null,
      isMenuVisible: false,
      links: [
        {
          to: '/about-me',
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
  watch: {
    $route() {
      this.closeMenu()
    },
  },
  mounted() {
    this.initialPath = this.$route.path
    this.throttleHandleScroll = throttle(this.handleScroll, 100)
    this.content = document.getElementById('content')
    this.content.addEventListener('scroll', this.throttleHandleScroll)
    window.addEventListener('scroll', this.throttleHandleScroll)
    this.scrolled = window.scrollY > 30
  },
  destroyed() {
    this.content.removeEventListener('scroll', this.throttleHandleScroll)
    window.removeEventListener('scroll', this.throttleHandleScroll)
  },
  methods: {
    toggleMenu() {
      this.isMenuVisible = !this.isMenuVisible
    },
    closeMenu() {
      this.isMenuVisible = false
    },
    handleScroll() {
      this.scrolled = this.content.scrollTop > 30 || window.scrollY > 30
    },
  },
}
</script>

<style lang="scss" scoped>
.header {
  width: 100%;
  position: fixed;
  z-index: 1;
  padding: 48px 80px 48px 0;
  @media screen and (max-width: 799px) {
    top: 0;
    left: 0;
    padding: 24px;
  }

  transition: padding 0.5s ease;
  &--scrolled {
    z-index: 1;
    background-color: white;
    padding: 16px;
    box-shadow: 0 0.5rem 1rem 0 rgba(grey, 0.2);
    @media screen and (min-width: 800px) {
      padding: 24px 80px 24px 0;
    }
  }
  &__home {
    font-size: 32px;
    @media screen and (min-width: 800px) {
      padding-left: 80px;
    }
    a {
      text-decoration: none;
    }
  }
  &__content {
    display: flex;
    justify-content: space-between;
    @media screen and (min-width: 800px) {
      justify-content: space-between;
    }
  }
  &__toggle {
    padding: 0;
    border: none;
    background: transparent;
    cursor: pointer;
    display: flex;
    transition: all 0.3s;
    &:hover,
    &:focus {
      outline: none;
    }
    @media screen and (min-width: 800px) {
      display: none;
    }
  }
}
.menu {
  display: flex;
  width: 100%;
  justify-content: flex-end;
  @media screen and (max-width: 799px) {
    display: block;
    position: absolute;
    padding-top: 32px;
    top: 100%;
    left: 0;
    &--hidden {
      display: none;
    }
  }
  &__links {
    margin: 0;
    padding: 0;
    list-style: none;
    float: left;
    clear: both;
    padding-left: 32px;
    @media screen and (min-width: 800px) {
      display: flex;
      align-items: center;
      padding-left: 0;
    }
  }
  &__link {
    display: block;
    margin-right: 24px;
    margin-bottom: 48px;
    font-size: 16px;
    font-family: 'Merriweather', sans-serif;
    font-weight: 500;
    @media screen and (min-width: 800px) {
      margin-bottom: 0;
    }
    a {
      text-decoration: none;
      color: black;
      border-bottom: 2px solid transparent;
      transition: border-bottom 0.3s;
    }
    &--current {
      /deep/ a {
        border-bottom: 2px solid black;
      }
    }
    &:hover {
      /deep/ a {
        border-bottom: 2px solid black;
      }
    }
    &:last-child {
      margin-right: 0;
    }
  }
}
.overlay {
  width: 100vw;
  height: 100vh;
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
  background: white;
}
</style>
