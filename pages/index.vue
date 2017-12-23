<template>
  <div>
      <h1 class="title">Films</h1>
      <div class="columns is-mobile is-multiline is-centered">
        <div class="column is-one-third-desktop" v-for="p in posts">
          <single-post-tile :post="p" />
        </div>
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
      let result = await axios.post(`${env.cockpit.apiUrl}/mediamanager/thumbnails?token=${env.cockpit.apiToken}`, {
        images: [p.Image],
        w: 300,
        h: 300,
        options: {
          quality: 200,
          mode: 'crop'
        }
      })

      console.log(result)

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
  padding: 1em;
}
.column{
  min-width: 200px;
}


</style>
