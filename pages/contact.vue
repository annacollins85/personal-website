<template>
  <div>
    <NavBar />
    <section class="contact">
      <h1 class="title contact__title">Get in touch ✍️</h1>
      <div class="contact__links">
        <a
          href="https://twitter.com/annacol19"
          target="_blank"
          aria-label="link to Twitter"
          rel="noopener"
          ><TwitterIcon
        /></a>
        <a
          href="https://www.linkedin.com/in/anna-collins/"
          target="_blank"
          aria-label="link to LinkedIn"
          rel="noopener"
          ><LinkedInIcon
        /></a>
        <a
          href="https://github.com/annacollins85"
          target="_blank"
          aria-label="link to GitHub"
          rel="noopener"
          ><GitHubIcon
        /></a>
        <a
          href="https://www.strava.com/athletes/23471847"
          target="_blank"
          aria-label="link to Strava"
          rel="noopener"
          ><StravaIcon
        /></a>
        <a
          href="mailto:annacollins85@gmail.com"
          target="_blank"
          aria-label="email anna@collins85@gmail.com"
          rel="noopener"
          ><GmailIcon
        /></a>
      </div>
    </section>
  </div>
</template>

<script>
import NavBar from '~/components/common/NavBar'
import TwitterIcon from '~/assets/icons/twitter.svg'
import LinkedInIcon from '~/assets/icons/linkedin.svg'
import GitHubIcon from '~/assets/icons/github.svg'
import StravaIcon from '~/assets/icons/strava.svg'
import GmailIcon from '~/assets/icons/gmail.svg'

export default {
  components: {
    NavBar,
    TwitterIcon,
    LinkedInIcon,
    GitHubIcon,
    StravaIcon,
    GmailIcon,
  },
}
</script>

<style lang="scss" scoped>
.contact {
  min-height: 100vh;
  padding: 0 56px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  &__title {
    margin-bottom: 48px;
    font-size: 24px;
    @media screen and (min-width: 600px) {
      font-size: 32px;
    }
  }
  &__links {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
  }
  a {
    text-decoration: none;
    &:hover {
      transition: all 0.3s;
      transform: translateY(-4px);
    }
    svg {
      margin-right: 12px;
      @media screen and (min-width: 400px) {
        margin-right: 24px;
      }
    }
    &:last-child {
      svg {
        margin-right: 0;
      }
    }
  }
}
</style>
