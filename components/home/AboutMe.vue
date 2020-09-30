<template>
  <div id="about-me" class="container">
    <section class="about-me">
      <div class="about-me__image">
        <img src="~/assets/images/face.png" />
      </div>
      <div class="about-me__text">
        <h2>
          <span class="title drop-cap">I</span>'m Anna, a mostly front-end but
          kind of full-stack developer 👩‍💻 I like Vue.js, algorithms, GraphQL and
          generally fiddling around learning new stuff. I'm a maths graduate
          from the UK who completed a coding bootcamp 3 years ago. Since then
          I've worked at Holaluz, Typeform and I'm currently working remotely
          for Codegram. I love sharing my passion for coding through giving
          workshops and mentorship to aspiring developers. As you can see I'm a
          fan of an emoji or two 😆. In my free time you can usually find me up
          a mountain on my bike or eating curry.
        </h2>
      </div>
    </section>
  </div>
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
}
.about-me {
  min-height: 100vh;
  padding: 0 56px 0 0;
  display: grid;
  grid-template-columns: 1fr 2fr;
  grid-template-rows: auto;
  grid-template-areas: 'image text text';
  &__image {
    grid-area: image;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    img {
      height: 300px;
      width: 300px;
      border-radius: 50%;
      object-fit: cover;
    }
  }
  &__text {
    grid-area: text;
    display: flex;
    align-items: center;
    margin-left: 36px;
    h2 {
      font-size: 18px;
      font-weight: 400;
      line-height: 2;
      max-width: 700px;
    }
  }
}
.drop-cap {
  font-size: 56px;
  line-height: 1;
}
</style>
