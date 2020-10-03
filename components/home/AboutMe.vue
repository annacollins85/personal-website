<template>
  <section id="about-me" class="container">
    <div class="about-me">
      <div class="about-me__image">
        <img src="~/assets/images/me.png" />
      </div>
      <div class="about-me__text">
        <span class="title drop-cap">I</span>'m Anna, a mostly front-end but
        kind of full-stack developer 👩‍💻 I like Vue.js, algorithms, GraphQL and
        generally fiddling around learning new stuff. I'm a maths graduate from
        the UK who completed a coding bootcamp 3 years ago. Since then I've
        worked at Holaluz, Typeform and I'm currently working remotely for
        Codegram. I love sharing my passion for coding through giving workshops
        and mentorship to aspiring developers. As you can see I'm a fan of an
        emoji or two 😆. In my free time you can usually find me up a mountain
        on my bike or eating curry.
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
    img {
      height: 120px;
      width: 120px;
      border-radius: 50%;
      object-fit: cover;
      @media screen and (min-width: 400px) {
        height: 200px;
        width: 200px;
      }
      @media screen and (min-width: 600px) {
        height: 230px;
        width: 230px;
      }
    }
    @media screen and (min-width: 800px) {
      margin-right: 56px;
    }
  }
  &__text {
    display: block;
    line-height: 1.2;
    @media screen and (min-width: 450px) {
      font-size: 18px;
      line-height: 1.4;
    }
    @media screen and (min-width: 800px) {
      max-width: 600px;
    }
  }
}
.drop-cap {
  font-size: 56px;
  line-height: 0.8;
}
</style>
