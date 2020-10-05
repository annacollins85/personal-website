<template>
  <div class="home">
    <NavBar />
    <AboutMe />
    <Footer />
  </div>
</template>

<script>
import NavBar from '~/components/common/NavBar'
import AboutMe from '~/components/about-me/AboutMe'
import Footer from '~/components/common/Footer'

export default {
  components: {
    NavBar,
    AboutMe,
    Footer,
  },
}
</script>
