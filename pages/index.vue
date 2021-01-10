<template>
  <div class="container w-screen align-content-center">
    <div class="max-w-sm bg-white shadow-lg rounded-lg overflow-hidden my-4 mx-auto">
      <GitHubProfile :username="`jaaneek`"/>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'
import GitHubProfile from "~/components/GitHubProfile";

export default {
  data() {
    const domain = process.server ? req.headers.host : window.location.hostname;

    return {
      title: domain,
      domain: domain,
    }
  },
  head() {
    return {
      title: this.title,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: `${this.domain} - Probably yet another bad domain purchase decision by @stemount.`,
        }
      ],
      bodyAttrs: {
        class: '',
      }
    }
  },
  components: {
    GitHubProfile,
    Logo
  }
}
</script>

<style>
a:link,
a:visited {
  color: #35495e;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 3rem;
  color: #35495e;
  letter-spacing: 1px;
  padding-bottom: 1em;
  margin-top: 1em;
}

.subtitle {
  font-weight: 300;
  font-size: 24px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

p {
  font-size: 14px;
}

.links {
  padding-top: 15px;
}
</style>
