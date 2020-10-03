<template>
  <div>
    <NavBar />
    <BlogPostList />
    <Footer />
  </div>
</template>

<script>
import NavBar from '~/components/common/NavBar'
import BlogPostList from '~/components/posts/BlogPostList'
import Footer from '~/components/common/Footer'

export default {
  components: {
    NavBar,
    BlogPostList,
    Footer,
  },
}
</script>
