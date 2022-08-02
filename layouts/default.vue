<template>
  <div id="app">
    <nav-bar />
    <Nuxt />
  </div>
</template>

<script>
import NavBar from '~/components/NavBar.vue'
export default {
  components: { NavBar },
  head() {
    return {
      titleTemplate: '%s - Real World Events',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content:'Where can you find all techniques in your computer?'
        }
      ]
    }
  }
}
</script>

<style>

</style>
