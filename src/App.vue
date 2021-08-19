<template>
  <div id="app">
    <div class="header">
      <div class="nav p-4">
        <h1 class="me-auto"><router-link to="/">B</router-link></h1>
        <div class="d-flex align-items-center nav-block">
          <router-link class="nav-pc" to="/">About</router-link>
          <router-link class="nav-pc" to="/single">Website</router-link>
          <router-link class="nav-pc" to="/single">Branding</router-link>
          <a class="burger" href="#" :class="{ 'active': burgerStatus == true }" @click.prevent="burgerStatus = !burgerStatus">
            <i></i>
          </a>
        </div>
      </div>
    </div>
    <router-view/>
  </div>
</template>
<script>
export default {
  data () {
    return {
      burgerStatus: false
    }
  }
}
</script>
<style lang="scss">
@import './assets/scss/main'
</style>
