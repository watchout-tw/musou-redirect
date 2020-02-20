<template>
  <main>
    國會無雙搬新家啦！出發～阿草帶你轉址中～～
    <img :src="img" height="400"/>
  </main>
</template>

<script>
import defaultImg from 'watchout-common-assets/images/default.gif'

export default {
  data () {
    return {
      img: defaultImg
    }
  },
  beforeMount () {
    window.location = 'https://musou.watchout.tw/'
  }
}
</script>
