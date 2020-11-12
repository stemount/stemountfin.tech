<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">
        {{ domain }}
      </h1>
      <h4 class="subtitle">
        <a href="https://ste.london">@stemount</a> productions present
      </h4>

      <p>proof that Vue/Nuxt can be ran in production</p>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

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
      ]
    }
  },
  components: {
    Logo
  }
}
</script>

<style>
a:link,
a:visited {
  color: #35495e; 
}
.container {
  margin: 0 2rem;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
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
