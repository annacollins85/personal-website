<template>
  <div>
    <NavBar />
    <TalksList />
    <Footer />
  </div>
</template>

<script>
import NavBar from '~/components/common/NavBar'
import TalksList from '~/components/speaking/TalksList'
import Footer from '~/components/common/Footer'

export default {
  components: {
    NavBar,
    TalksList,
    Footer,
  },
}
</script>
