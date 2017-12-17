<template>
  <div class="card">
    <header class="card-header">
      <div class="card-header-title is-centered">
          {{ post.Title }}
      </div>
    </header>

    <div class="card-image">
      <img v-bind:src="post.ImageUrl" />
    </div>

    <div class="card-content">
      <div class="content">
        {{ post.Content }}
      </div>
    </div>

    <div class="card-footer">
    </div>
  </div>
</template>

<style>

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
