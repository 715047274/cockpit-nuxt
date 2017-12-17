<template>
  <div class="columns is-mobile is-multiline is-centered">
    <div class="column is-one-third-desktop" v-for="p in posts">
      <single-post-tile :post="p" />
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import SinglePostTile from '~/components/SinglePostTile.vue'

export default {
  components: {SinglePostTile},
  async asyncData ({env, params}) {
    let {data} = await axios.get(`${env.cockpit.apiUrl}/collections/get/Post?token=${env.cockpit.apiToken}`)

    let posts = await Promise.all(await data.map(async (p) => {
      let result = await axios.post(`${env.cockpit.apiUrl}/mediamanager/images?token=${env.cockpit.apiToken}`, {
        images: [p.Image],
        w: 300,
        h: 300,
        options: {
          quality: 80,
          mode: 'resize'
        }
      })

      p.ImageUrl = `${env.cockpit.baseUrl}${result.data[p.Image]}`
      return p
    }))

    return {
      posts
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
