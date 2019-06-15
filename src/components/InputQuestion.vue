<!-- src/components/InputQuestion.vue -->

<template>
  <form @submit.prevent="handleSubmit" class="input-question">
    <p class="orangeb">自分売り込みの提案書ができます</p>
    <p>このジェネレーターでできるのは自分を売り込むツール。平たくいうと、「おれはこんなにすばらしいので～してくれ」ということをアピールする資料です。</p>
    <p>目的は4種類。相手の名前と自分の名前の文字数がやたらと短かったりするが、それはそういうものだと思って納得してください。</p>
    <p>ではどうぞ。</p>
    <input name="t1" value type="hidden">
    <input name="ct" value="0" type="hidden">
    <p class="orangeb">step 1 / 6</p>
    <p>
      相手の名前をどうぞ（6文字以内）
      <br>
      <input type="text" v-model="aite" size="40" maxlength="12" required>
    </p>
    <p>
      あなたのなまえ（6文字以内）
      <br>
      <input type="text" v-model="anata" size="40" maxlength="12" required>
    </p>
    <p>提案内容</p>
    <p>
      <input type="radio" id="one" value="1" v-model="naiyo">
      <label for="one">就職させてくれ</label>
      <br>
      <input type="radio" id="two" value="2" v-model="naiyo">
      <label for="two">結婚してくれ</label>
      <br>
      <input type="radio" id="three" value="3" v-model="naiyo">
      <label for="three">わたしの弟子になれ</label>
      <br>
      <input type="radio" id="four" value="4" v-model="naiyo">
      <label for="four">パン買ってきて</label>
      <br>
    </p>
    <button>次へ</button>
  </form>
</template>

<script>

export default {
  data() {
    return {
      aite: "",
      anata: "",
      naiyo: 1
    };
  },
  methods: {
    handleSubmit() {
      let dateString = 
      this.$emit("start", { aite: this.aite, anata: this.anata, naiyo: this.naiyo });
    }
  }
};
</script>

<style scoped>
.orangeb {
  color: #ff6600;
  font-weight: bold;
}
.input-question {
  margin-bottom: 24px;
  padding-bottom: 24px;
  border-bottom: dotted 1px #c6c6c6;
}
h3 {
  font-size: 1em;
}
dd {
  margin: 16px 0 0;
  padding: 0 0 8px 0;
}
button {
  width: 60px;
}
input[type="text"] {
  margin-right: 20px;
}
</style>