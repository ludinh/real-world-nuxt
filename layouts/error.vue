<template>
  <div class="wrap-content">
    <div class="title">
      {{ message }}
    </div>
    <p v-if="statusCode === 404">
      <nuxt-link to="/">
        Return to HomePage.
      </nuxt-link>
    </p>
  </div>
</template>

<script>
export default {
  props: {
    error: {
      type: Object,
      default: null,
    },
  },
  head() {
    return {
      title: this.message,
    };
  },
  computed: {
    statusCode() {
      return (this.error && this.error.statusCode) || 500;
    },
    message() {
      return this.error.message;
    },
  },
};
</script>

<style>
</style>
