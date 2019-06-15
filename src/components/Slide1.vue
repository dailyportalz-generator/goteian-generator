<template>
  <table
    width="540"
    border="0"
    cellpadding="0"
    cellspacing="0"
    class="slide"
  >
    <tr>
      <td height="70" valign="bottom">
        <span class="style25" style="padding-left:30px">{{aite}} 様</span>
      </td>
    </tr>
    <tr>
      <td height="60">
        <div align="center" class="style35">{{text3a}}</div>
      </td>
    </tr>
    <tr>
      <td height="120">&nbsp;</td>
    </tr>
    <tr>
      <td height="155">
        <div align="center" class="style25">
          <p>
            {{anata}}
            <br>
            {{hiduke}}
          </p>
        </div>
      </td>
    </tr>
  </table>
</template>
<script>
export default {
  props: {
    aite: String,
    text3a: String,
    anata: String,
    hiduke: String
  }
};
</script>

<style scoped>
body{
  color:black
}
table {
  margin-bottom: 30px;
}
.style35 {
    font-size: 35px;
    font-weight: 800;
}
.style25 {
    font-size: 25px;
    font-weight: 400;
    line-height: 130%;
}
.slide {
    font-family: "ＭＳ Ｐゴシック", Osaka, "ヒラギノ角ゴ Pro W3", "メイリオ";
}

table {
  background: url('../assets/001.gif');
}
</style>