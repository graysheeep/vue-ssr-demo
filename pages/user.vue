<template>
  <section class="container">
    <div @click="loadData">
      User Page
    </div>
    <h3 @click="heihei">heihei</h3>
    <h2>{{ user.body }}</h2>
    <h2>{{ user.title }}</h2>
  </section>
</template>

<script>
import * as axios from 'axios'
import AppLogo from '~/components/AppLogo.vue'

export default {
  data () {
    return {
      user: {}
    }
  },

  components: {
    AppLogo
  },

  methods: {
    async loadData () {
      const resp = await axios.get('https://jsonplaceholder.typicode.com/posts/1')
      this.user = resp.data
    },

    heihei () {
      console.log('123')
    }
  }
}
</script>

<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
