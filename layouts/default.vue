<template>
  <div class="default">
    <Nuxt id="content" :key="$route.fullPath" />
  </div>
</template>

<style lang="scss" scoped>
.default {
  position: relative;
}
</style>
