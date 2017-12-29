
<transition
  v-on:after-enter="afterEnter"
></transition>
<template>
  <div class="columns is-mobile is-multiline is-centered">
    <div class="content" v-html="$route.params.postContent">
    </div>
  </div>
</template>


<script>

export default {
  transition: {
    name: 'detail',
    mode: 'out-in',
    methods: {
      beforeEnter: function (el) {
        console.log('back')
        history.back()
      },
      leave: function (el, done) {
        console.log('back')
        history.back()
        done()
      }
    }
  }
}
</script>

<style>



</style>
