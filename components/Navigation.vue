<template>
  <div class="navbar-menu">
      <div class="navbar-end">
        <a class="navbar-item">
          Home
        </a>
        <div class="navbar-item has-dropdown">
          <a class="navbar-link">
            Films
          </a>

          <div class="navbar-dropdown">
            <!-- Other navbar items -->
          </div>
        </div>
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
