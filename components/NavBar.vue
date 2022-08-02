<template>
  <div class="nav">
    <nuxt-link to="/" class="brand">
      Real World Events
    </nuxt-link>

  <nav>
    <nuxt-link to="/" class="nav-item">
      List
    </nuxt-link>
    <nuxt-link to="/event/create" class="nav-item">
      Create
    </nuxt-link>
  </nav>
  </div>
</template>

<script>
export default {
   name: 'nav-bar'
};
</script>

<style>
.brand{font-family: 'Montserrat', sans-serif;font-weight: 700;font-size:1.5rem;color:#42b883;text-decoration: none;}
.nav{display: flex;justify-content: space-between;align-items: center;height:70px;width:min(1100px, 90vw);position:relative;margin:auto}
.nav .nav-item{box-sizing: border-box;margin:0;color:#444;text-decoration: none;padding:8px 15px;border-radius: 5px;transition:all 0.2s ease-in-out;}
.nav .nav-item:hover{background-color:#efefef;}
.nav .nav-item.nuxt-link-exact-active{color:#fff;background-color: #42b883;}
</style>
