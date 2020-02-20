<template>
  <main>
    國會無雙搬新家啦！出發～阿草帶你轉址中～～
    <img :src="img" height="400"/>
  </main>
</template>

<script>
import articleTable from '~/data/musou-migration.json'
import defaultImg from 'watchout-common-assets/images/default.gif'

function findMapping (target) {
  return articleTable.migration.find(item => {
    return item.musou_id.toString() === target
  })
}

export default {
  beforeMount () {
    let mapping = null
    if (/^focuses\/[0-9]+$/.test(this.$route.params.pathMatch)) {
      mapping = findMapping(this.$route.params.pathMatch.substring(8))
    } else if (/^videos\/[0-9]+$/.test(this.$route.params.pathMatch)) {
      mapping = findMapping(this.$route.params.pathMatch.substring(7))
    }
    if (mapping) {
      window.location = `https://musou.watchout.tw/read/${mapping.fs_id}`
    } else {
      window.location = 'https://musou.watchout.tw/'
    }
  },
  data () {
    return {
      img: defaultImg
    }
  }
}
</script>
