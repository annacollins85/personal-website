<template>
  <div class="home">
    <NavBar />
    <Intro />
    <AboutMe />
    <Footer />
  </div>
</template>

<script>
import NavBar from '~/components/common/NavBar'
import AboutMe from '~/components/home/AboutMe'
import Intro from '~/components/home/Intro'
import Footer from '~/components/common/Footer'

export default {
  components: {
    NavBar,
    AboutMe,
    Intro,
    Footer,
  },
  data() {
    return {
      currentSection: 'about-me',
      sections: ['intro', 'about-me', 'posts', 'workshop'],
    }
  },
}
</script>

<style lang="scss" scoped>
.home {
  overflow: scroll;
  height: 100vh;
  scroll-snap-points-y: repeat(100vh);
  scroll-snap-type: y mandatory;
  @media screen and (max-width: 750px) {
    scroll-padding-top: 24px;
  }
}
::-webkit-scrollbar {
  width: 0;
  background: transparent;
}
</style>
