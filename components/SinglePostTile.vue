<template>
  <div class="card">
    <header class="card-header">
      <div class="card-header-title is-centered">
          <p class="title is-4">
            {{ post.Title }}
          </p>
      </div>
    </header>

    <div class="card-image">
      <img v-bind:src="post.ImageUrl" />
    </div>

    <div class="card-content">
      <div class="content">
          <nuxt-link :to="{ name: 'detail', params: { postContent: post.Content }}">READ MORE</nuxt-link>
      </div>

    </div>

    <div class="card-footer">
    </div>
  </div>
</template>

<style>
  .card-image{
    text-align: center;
    padding: 2em 1em 0;
  }
  .card{
    height: 100%;
    display: flex;
    flex-direction: column;
  }
  .card-footer{
    margin-top: auto;
  }
</style>

<script>
export default {
  props: {
    post: {
      type: Object,
      required: true
    }
  }
}
</script>
