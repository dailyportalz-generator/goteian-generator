<template>
  <form @submit.prevent="handleSubmit" class="input-question">
    <p class="orangeb">step 4 / 7 あなたの長所は</p>
    <p>
      <input type="radio" id="one" value="1" v-model="naiyo">
      <label for="one">我慢強い</label>
      <br>
      <input type="radio" id="two" value="2" v-model="naiyo">
      <label for="two">愛想笑いが得意</label>
      <br>
      <input type="radio" id="three" value="3" v-model="naiyo">
      <label for="three">ごはんを食べるのが早い</label>
      <br>
      <input type="radio" id="four" value="4" v-model="naiyo">
      <label for="four">特にない</label>
      <br>
    </p>
    <button>次へ</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      naiyo: 1
    };
  },
  methods: {
    handleSubmit() {
      let dateString = this.$emit("start", {

        naiyo: this.naiyo
      });
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