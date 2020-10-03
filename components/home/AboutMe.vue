<template>
  <section id="about-me" class="container">
    <div class="about-me">
      <div v-in-viewport.once="'-200px 0px'" class="about-me__image">
        <img src="~/assets/images/me.png" />
      </div>
      <div class="about-me__text">
        <span class="title drop-cap">I</span>'m Anna, a mostly front-end but
        kind of full-stack developer 👩‍💻 I like Vue.js, algorithms, GraphQL and
        generally fiddling around learning new stuff. I'm a maths graduate from
        the UK but have been living in Sunny Barcelona ☀️ for the past 9 years
        where I've worked for Holaluz, Typeform and currently I'm working
        remotely for Codegram. I love sharing my passion for coding through
        giving workshops and mentorship to aspiring developers. In my free time
        you can usually find me up a mountain on my bike 🚲.
      </div>
    </div>
  </section>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.container {
  position: relative;
  display: flex;
  flex-direction: column;
  scroll-snap-align: start;
  padding-bottom: 48px;
  max-width: 1024px;
  margin: 0 auto;
}
.about-me {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  padding: 0 32px;
  @media screen and (min-width: 600px) {
    padding: 0 56px;
  }
  @media screen and (min-width: 600px) {
    padding: 0 56px;
  }
  @media screen and (min-width: 800px) {
    flex-direction: row;
  }
  &__image {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 120px;
    min-width: 120px;
    @media screen and (min-width: 400px) {
      min-height: 200px;
      min-width: 200px;
    }
    @media screen and (min-width: 600px) {
      min-height: 230px;
      min-width: 230px;
    }
    @media screen and (min-width: 800px) {
      margin-right: 56px;
    }
    img {
      height: 20px;
      width: 20px;
      border-radius: 50%;
      object-fit: cover;
      transition: all 1s ease-in;
    }
    &.in-viewport {
      img {
        height: 120px;
        width: 120px;
        @media screen and (min-width: 400px) {
          height: 200px;
          width: 200px;
        }
        @media screen and (min-width: 600px) {
          height: 230px;
          width: 230px;
        }
      }
    }
  }
  &__text {
    display: block;
    line-height: 1.2;
    max-width: 626px;
    @media screen and (min-width: 450px) {
      font-size: 18px;
      line-height: 1.4;
    }
  }
}
.drop-cap {
  font-size: 56px;
  line-height: 0.8;
}
</style>
