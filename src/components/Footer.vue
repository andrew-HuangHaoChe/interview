<template>
  <div>
    <footer>
      <div class="footer-border">
        <div class="container">
          <div class="row">
            <div class="col-12 col-md-6">
              <div class="d-flex">
                <div class="footer-logo">
                  <h2>B</h2>
                </div>
                <div>
                  <ul class="d-flex list-unstyled footer-link">
                    <li><router-link to="/">About</router-link> </li>
                    <li><router-link to="/single">Website</router-link></li>
                    <li><router-link to="/single">Branding</router-link></li>
                  </ul>
                  <ol class="list-unstyled">
                    <li>T. 02-2885-8586</li>
                    <li>E. info@blockstudio.tw</li>
                    <li>3F., No.2, Ln. 80, Sec. 4, Chengde Rd., Shilin Dist., Taipei City 111, Taiwan</li>
                  </ol>
                </div>
              </div>
            </div>
            <div class="col-12 col-md-6">
              <div class="d-flex justify-content-start justify-content-md-end">
                <ul class="d-flex list-unstyled mb-0 social-link">
                  <li><a target="blank" href="https://www.facebook.com/blockstudiotw"><img src="../assets/img/index/facebook.svg" alt="facebook"></a></li>
                  <li><a target="blank" href="https://www.instagram.com/blockstudiotw/"><img src="../assets/img/index/instagram.svg" alt="instagram"></a></li>
                  <li><a target="blank" href="https://www.youtube.com/watch?v=LKJZQ7dbu14"><img src="../assets/img/index/youtube.svg" alt="youtube"></a></li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
      <h2 class="text-center footer-copy-right">Block Studio©2018 Copyright. All Rights Reserved.</h2>
      <transition name="opacity">
        <div class="scrollToTop" id="scrollToTop" @click="scrolltotop"><i class="fas fa-chevron-up"></i></div>
      </transition>
      </footer>
  </div>
</template>

<script>
export default {
  name: 'pageFooter',
  methods: {
    scrolltotop () {
      window.scrollTo(0, 0)
    },
    onScroll () {
      const scrollTop = document.documentElement.scrollTop + document.body.scrollTop
      document.getElementById('scrollToTop').style.opacity = 0
      if (scrollTop > 0) {
        document.getElementById('scrollToTop').style.visibility = 'visible'
        document.getElementById('scrollToTop').style.opacity = 1
      } else {
        document.getElementById('scrollToTop').style.visibility = 'hidden'
      }
    }
  },
  mounted () {
    document.addEventListener('scroll', this.onScroll)
  },
  beforeDestroy () {
    document.removeEventListener('scroll', this.onScroll)
  }
}
</script>
