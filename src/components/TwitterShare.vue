<template>
  <div class="result">
      <p class="result_build">
        <button type="button" @click="handleClickRestart">もう一度つくる</button>
      </p>
      <p class="result_share">
        <input type="text" class="result_shareurl" readonly :value="shareUrl">
        <a target="_blank" :href="twitterUrl">つぶやく</a>
      </p>
  </div>
</template>

<script>
import { stringify } from 'querystring'
export default {
 props: {
    questions: Object,
    step: Number
  },
computed: {
    shareUrl() {
      const shareData = {
        ...this.questions.target,
        ...this.questions,
        target: null,
        share: 1
      }
      delete shareData.target
      
      return `https://dailyportalz.jp/kiji/goteian-generator?${stringify(
        shareData
      )}`
    },
    twitterUrl() {
      return `https://twitter.com/intent/tweet?text=ご提案ジェネレータ―&url=${encodeURIComponent(
        this.shareUrl
      )}`
    }
},
methods: {
    handleClickRestart() {
      location.href = location.href.replace(location.search, '')
    }
  }


}

</script>


    
