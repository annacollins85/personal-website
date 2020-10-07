<template>
  <section class="intro">
    <client-only>
      <vue-typer
        class="title intro__typewriter"
        :text="[
          'Hello! 👋 I\'m Anna,',
          'a JavaScript developer 👩‍💻',
          'Welcome to my web! 🕸',
        ]"
        :erase-delay="500"
        :pre-erase-delay="500"
        :repeat="0"
      />
    </client-only>
  </section>
</template>

<style lang="scss" scoped>
.intro {
  height: 100vh;
  padding: 0 32px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  white-space: wrap;
  @media screen and (min-width: 600px) {
    padding: 0 56px;
  }
  &__typewriter {
    font-size: 18px;
    @media screen and (min-width: 350px) {
      font-size: 20px;
    }
    @media screen and (min-width: 375px) {
      font-size: 24px;
    }
    @media screen and (min-width: 605px) {
      font-size: 28px;
    }
    @media screen and (min-width: 800px) {
      font-size: 32px;
    }
  }
}
/deep/ .vue-typer .custom.char.selected {
  background-color: rgba(3, 252, 198, 0.4);
}
</style>
