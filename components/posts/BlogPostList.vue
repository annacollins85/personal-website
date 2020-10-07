<template>
  <section class="blog-posts">
    <h1 class="title blog-posts__title">Read all about it 🗞️</h1>
    <div class="blog-posts__list">
      <a
        v-for="post in blogPosts"
        :key="post.title"
        class="post"
        :href="post.url"
        rel="noopener"
        target="_blank"
        :aria-label="`go to ${post.title} blog post`"
      >
        <div class="post__image">
          <img :src="post.image" />
        </div>
        <div class="post__info">
          <h3 class="title post__title">{{ post.title }}</h3>
          <p>{{ post.lead }}</p>
          <p class="post__date">{{ post.date }}</p>
        </div>
      </a>
    </div>
  </section>
</template>

<script>
import posts from '~/blog-posts.json'

export default {
  data() {
    return {
      blogPosts: posts,
    }
  },
}
</script>

<style lang="scss" scoped>
.blog-posts {
  padding: 96px 32px 160px;
  margin: 0 auto;
  max-width: 1024px;
  @media screen and (min-width: 600px) {
    padding: 140px 56px 260px;
  }
  &__title {
    margin-bottom: 56px;
    font-size: 24px;
    @media screen and (min-width: 600px) {
      font-size: 32px;
    }
  }
  &__list {
    display: flex;
    flex-direction: column;
    @media screen and (min-width: 600px) {
      display: grid;
      grid-template-columns: 1fr 1fr;
      grid-gap: 56px;
    }
  }
}
.post {
  color: black;
  text-decoration: none;
  box-shadow: 0 0.5rem 1rem 0 rgba(grey, 0.2);
  margin-bottom: 48px;
  @media screen and (min-width: 600px) {
    margin-bottom: 0;
  }
  &:hover {
    transition: all 0.3s;
    transform: translate(2px, -2px);
  }
  &__image {
    height: 200px;
    width: 100%;
    @media screen and (min-width: 450px) {
      height: 280px;
    }
    @media screen and (min-width: 600px) {
      height: 180px;
    }
    @media screen and (min-width: 700px) {
      height: 200px;
    }
    @media screen and (min-width: 800px) {
      height: 230px;
    }
    @media screen and (min-width: 900px) {
      height: 250px;
    }
    @media screen and (min-width: 1024px) {
      height: 280px;
    }
    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }
  &__info {
    padding: 0 24px;
  }
  &__title {
    margin-top: 24px;
    font-size: 24px;
    margin-bottom: 16px;
  }
  &__date {
    color: grey;
    margin: 12px 0 24px;
  }
}
</style>
