<template>
  <table
    width="540"
    border="0"
    cellpadding="0"
    cellspacing="0"
    background="http://portal.nifty.com/2010/02/28/b/img/005.gif"
    class="slide"
  >
    <tr>
      <td width="22" valign="top">&nbsp;</td>
      <td width="145" valign="top">&nbsp;</td>
      <td width="208" height="170" align="center" valign="bottom">&nbsp;</td>
      <td width="165" valign="top">&nbsp;</td>
    </tr>
    <tr>
      <td height="100" valign="top">&nbsp;</td>
      <td width="145" align="right" valign="middle" class="style25">
        <img :src="meshiImages[text7]" width="100" height="100">
      </td>
      <td valign="top">&nbsp;</td>
      <td valign="middle" class="style25">%text3%</td>
    </tr>
    <tr>
      <td height="135" valign="top">&nbsp;</td>
      <td width="145" valign="top">&nbsp;</td>
      <td valign="top">&nbsp;</td>
      <td valign="top">&nbsp;</td>
    </tr>
  </table>
</template>

<script>
export default {
  props: {
    text7: Number
  },
  computed: {
    meshiImages() {
      return [
        null,
        require("../assets/7_1.jpg"),
        require("../assets/7_2.jpg"),
        require("../assets/7_3.jpg"),
        require("../assets/7_4.jpg")
      ];
    }
  }
};
</script>
<style scoped>
table {
  margin-bottom: 20px;
}
</style>