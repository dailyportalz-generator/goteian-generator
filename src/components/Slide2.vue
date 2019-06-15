<template>
  <table width="540" border="0" cellpadding="0" cellspacing="0" class="slide">
    <tr>
      <td height="250" colspan="3" valign="bottom">
        <p>&nbsp;</p>
      </td>
    </tr>
    <tr>
      <td width="29" height="108" valign="top">&nbsp;</td>
      <td width="252" valign="top" class="style25">{{aite}}様{{text4}}</td>
      <td width="259" valign="top">&nbsp;</td>
    </tr>
    <tr>
      <td height="47" valign="top">&nbsp;</td>
      <td valign="top">&nbsp;</td>
      <td valign="top">&nbsp;</td>
    </tr>
  </table>
</template>
<script>
export default {
  props: {
    aite: String,
    text4: String
  }
};
</script>

<style scoped>
.style25 {
  font-size: 25px;
  font-weight: 400;
  line-height: 130%;
}
table {
  margin-bottom: 30px;
  background: url("../assets/002.gif");
}
</style>