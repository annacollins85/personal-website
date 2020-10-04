<template>
  <section class="talks">
    <h1 class="title talks__title">Speaking 🗣️</h1>
    <div v-for="talk in talksList" :key="talk.title">
      <a
        v-if="talk.url"
        :href="talk.url"
        aria-label="link to watch talk"
        target="_blank"
        class="talk talk--link"
      >
        <div v-in-viewport.once class="talk__image">
          <img :src="talk.image" />
        </div>
        <div>
          <p class="talk__type">{{ talk.type }}</p>
          <div class="talk__header">
            <h3 class="title talk__title">{{ talk.title }}</h3>
            —
            <p class="talk__watch">Watch 📹</p>
          </div>
          <p>{{ talk.lead }}</p>
          <p class="talk__date">{{ talk.location }}—{{ talk.date }}</p>
        </div>
      </a>
      <div v-else class="talk">
        <div v-in-viewport.once class="talk__image">
          <img :src="talk.image" />
        </div>
        <div>
          <p class="talk__type">{{ talk.type }}</p>
          <h3 class="title talk__title">{{ talk.title }}</h3>
          <p class="talk__date">{{ talk.location }}—{{ talk.date }}</p>
          <p>{{ talk.lead }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import talks from '~/talks.json'

export default {
  data() {
    return {
      talksList: talks,
    }
  },
}
</script>

<style lang="scss" scoped>
.talks {
  padding: 96px 32px 0;
  margin: 0 auto;
  max-width: 1024px;
  @media screen and (min-width: 800px) {
    padding: 140px 56px 160px;
  }
  &__title {
    margin-bottom: 56px;
    font-size: 24px;
    @media screen and (min-width: 600px) {
      font-size: 32px;
    }
  }
}
.talk {
  color: black;
  text-decoration: none;
  margin-bottom: 56px;
  display: flex;
  align-items: center;
  flex-direction: column;
  @media screen and (min-width: 600px) {
    flex-direction: row;
  }
  &__image {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 160px;
    min-width: 160px;
    @media screen and (min-width: 600px) {
      margin-right: 32px;
    }
    img {
      height: 0;
      width: 0;
      border-radius: 50%;
      object-fit: cover;
      transition: height 0.5s ease-in, width 0.5s ease-in;
    }
    &.in-viewport {
      img {
        height: 160px;
        width: 160px;
      }
    }
  }
  &--link {
    &:hover {
      transition: all 0.3s;
      transform: translate(2px, -2px);
      /deep/ img {
        border: 3px solid rgba(3, 252, 198, 0.4);
      }
    }
  }
  &__header {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    margin-bottom: 16px;
  }
  &__title {
    margin-top: 12px;
    padding-right: 12px;
    font-size: 24px;
    margin-bottom: 16px;
  }
  &__watch {
    padding-left: 12px;
  }
  &__type {
    text-transform: uppercase;
    font-size: 14px;
    color: grey;
  }
  &__date {
    color: grey;
    margin: 12px 0 16px;
  }
}
</style>
