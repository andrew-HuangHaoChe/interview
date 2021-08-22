<template>
  <div id="app">
    <div class="header" :class="{ 'single-header': pageType == 'single' }">
      <transition name="slide">
        <div class="side-menu" v-if="burgerStatus">
          <div class="d-flex justify-content-end close-side">
            <!-- <a class="burger-close" href="#" :class="{ 'active': burgerStatus == false }" @click.prevent="burgerStatus = !burgerStatus">
              <i></i>
            </a> -->
          </div>
          <ul class="mb-0 list-unstyled side-content">
            <li><router-link class="text-white" to="/">About</router-link></li>
            <li><router-link class="text-white" to="/single">Website</router-link></li>
            <li><router-link class="text-white" to="/single">Branding</router-link></li>
            <h4>B</h4>
          </ul>
          <div class="side-footer">
            <ul class="list-unstyled side-footer-content">
              <li>T. 02-2885-8586</li>
              <li>E. info@blockstudio.tw</li>
              <li>3F., No.2, Ln. 80, Sec. 4, Chengde Rd., Shilin Dist.,</li>
              <li>Taipei City 111, Taiwan</li>
            </ul>
            <ul class="d-flex list-unstyled mb-0">
              <li><img src="./assets/img/index/facebook.svg" alt="facebook"></li>
              <li><img src="./assets/img/index/instagram.svg" alt="instagram"></li>
              <li><img src="./assets/img/index/youtube.svg" alt="youtube"></li>
            </ul>
          </div>
        </div>
      </transition>
      <div class="nav p-4 d-flex align-items-center" :class="{ 'h100': pageType !== 'index', 'bg-white': pageType == 'single' }">
        <h1 class="me-auto mb-0" :class="{ 'single-h1': pageType == 'single' }"><router-link to="/" :class="{ 'text-black': pageType == 'single' }">B</router-link></h1>
        <div class="d-flex align-items-center nav-block">
          <router-link :class="{ 'text-dark': pageType == 'single' }" class="nav-pc" to="/">About</router-link>
          <router-link :class="{ 'text-dark': pageType == 'single' }" class="nav-pc" to="/single">Website</router-link>
          <router-link :class="{ 'text-dark': pageType == 'single' }" class="nav-pc" to="/single">Branding</router-link>
          <p class="burger-transparent"></p>
          <a class="burger" href="#" :class="{ 'active': burgerStatus == true, 'light-burger': pageType == 'single' }" @click.prevent="burgerStatus = !burgerStatus">
            <i></i>
          </a>
        </div>
      </div>
      <div class="banner-content text-white" v-if="pageType == 'index'">
        <div class="container">
          <div class="row">
            <div class="col-md-12 d-flex flex-column h-100 align-items-center">
              <h2 class="text-center">Commercial builders with pride – <br> workmanship that values quality.</h2>
              <p class="text-center sub-title">Acclaim Contractors are a highly specialised local business with over 20 years building and civil industry<br>
                experience with many accolades, commendations and awards recognising their workmanship.Acclaim<br>
                Contractors are a highly specialised local business with over 20 years building .
              </p>
            </div>
          </div>
          <p class="copy-right">Block Studio©2018 Copyright. All Rights Reserved.</p>
        </div>
        <div class="social-btn-group p-4 d-flex w-100">
          <ul class="list-unstyled d-flex mb-0">
            <li><img src="./assets/img/index/facebook.svg" alt=""></li>
            <li><img src="./assets/img/index/instagram.svg" alt=""></li>
            <li><img src="./assets/img/index/youtube.svg" alt=""></li>
          </ul>
          <span class="scroll mb-0">Scroll</span>
        </div>
      </div>
    </div>
    <router-view/>
  </div>
</template>
<script>
import image from './assets/img/index/banner.png'
export default {
  data () {
    return {
      burgerStatus: false,
      indexBanner: image,
      pageType: ''
    }
  },
  created () {
    if (this.$route.path === '/') {
      this.pageType = 'index'
    }
  },
  watch: {
    '$route' (to, from) {
      const vm = this
      switch (to.path) {
        case '/':
          console.log('index')
          vm.pageType = 'index'
          break
        case '/single':
          console.log('single')
          vm.pageType = 'single'
          break
      }
    }
  }
}
</script>
<style lang="scss">
@import './assets/scss/main';
.slide-enter-active, .slide-leave-active {
  transition: transform 0.2s ease;
}
.slide-enter, .slide-leave-to {
  transform: translateX(100%);
  transition: all 150ms ease-in 0s;
}
</style>
