<template>
  <section id="intro" class="container">
    <div class="intro">
      <client-only>
        <vue-typer
          class="title intro__typewriter"
          text="Hello! 👋 I'm Anna, a JavaScript developer"
          :erase-delay="500"
          :pre-erase-delay="500"
          :repeat="0"
        />
        <vue-typer
          class="title intro__typewriter-mobile"
          :text="['Hello! 👋 I\'m Anna,', 'a JavaScript developer']"
          :erase-delay="500"
          :pre-erase-delay="500"
        />
      </client-only>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.container {
  position: relative;
  display: flex;
  flex-direction: column;
  scroll-snap-align: start;
}
.intro {
  height: 100vh;
  margin: 0 auto;
  padding: 0 32px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  white-space: wrap;
  @media screen and (min-width: 600px) {
    padding: 0 56px;
  }
  &__typewriter {
    display: none;
    @media screen and (min-width: 605px) {
      display: block;
      font-size: 24px;
    }
    @media screen and (min-width: 800px) {
      font-size: 28px;
    }
  }
  &__typewriter-mobile {
    font-size: 18px;
    @media screen and (min-width: 350px) {
      font-size: 20px;
    }
    @media screen and (min-width: 375px) {
      font-size: 24px;
    }
    @media screen and (min-width: 604px) {
      display: none;
    }
  }
}
.chevron {
  text-align: center;
  text-decoration: none;
  font-size: 36px;

  @media screen and (min-width: 800px) {
    padding-bottom: 0.8rem;
  }
}
/deep/ .vue-typer .custom.char.selected {
  background-color: rgba(3, 252, 198, 0.4);
}
</style>
