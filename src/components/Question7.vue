<template>
  <div>
    <p class="orangeb">step 7 / 7 完成です</p>
    <p>これであなたの提案書ができました。友達に見せたりツイッターやブログに書くときは下のURLをご利用ください（友達に見せるときは見せても怒らなさそうかどうかを判断してからにしてください）。</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      naiyo: 1
    };
  },
  methods: {}
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