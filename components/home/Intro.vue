<template>
  <div id="intro" class="container">
    <section class="intro">
      <div />
      <h1 class="title">Hello! 👋 I'm Anna, a JavaScript developer</h1>
      <div class="chevron">⌄</div>
    </section>
  </div>
</template>

<style lang="scss" scoped>
.container {
  position: relative;
  display: flex;
  flex-direction: column;
  scroll-snap-align: start;
}
.intro {
  min-height: 100vh;
  margin: 0 auto;
  padding: 0 56px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  white-space: wrap;
}
.chevron {
  text-align: center;
  text-decoration: none;
  font-size: 36px;
  padding-bottom: 0.25rem;
}
</style>
