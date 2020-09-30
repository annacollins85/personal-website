<template>
  <div id="workshop" class="container">
    <section class="workshop">
      <div class="workshop__see-all">
        <nuxt-link to="workshop">See all workshop</nuxt-link>
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
.workshop {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  min-height: 100vh;
  max-width: 900px;
  margin: 0 auto;
  padding: 121px 56px 0;
  &__title {
    font-size: 24px;
  }
  &__see-all {
    margin: 24px 0;
    text-align: center;
    a {
      text-decoration: none;
      color: black;
      font-weight: 400;
      border-bottom: 1px solid transparent;
      transition: border-bottom 0.3s;
      &:hover {
        border-bottom: 1px solid black;
      }
    }
  }
}
</style>
