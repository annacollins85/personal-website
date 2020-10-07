<template>
  <div class="home">
    <NavBar />
    <AboutMe />
  </div>
</template>

<script>
import NavBar from '~/components/common/NavBar'
import AboutMe from '~/components/about-me/AboutMe'

export default {
  components: {
    NavBar,
    AboutMe,
  },
}
</script>
