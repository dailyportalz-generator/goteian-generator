<template>
 
  <table
    width="540"
    border="0"
    cellpadding="0"
    cellspacing="0"
    background="http://portal.nifty.com/2010/02/28/b/img/003.gif"
    class="slide"
  >
    <tr>
      <td height="89" colspan="4" valign="bottom">
        <p>&nbsp;</p>
      </td>
    </tr>
    <tr>
      <td width="50" height="128" valign="top">&nbsp;</td>
      <td colspan="2" valign="top" class="style25">{{text5a}} {{anata}} {{text5b}}</td>
      <td width="47" valign="top">&nbsp;</td>
    </tr>
    <tr>
      <td height="20" valign="top">&nbsp;</td>
      <td colspan="2" valign="top">&nbsp;</td>
      <td valign="top">&nbsp;</td>
    </tr>
    <tr>
      <td height="50" valign="top">&nbsp;</td>
      <td width="275" valign="top">&nbsp;</td>
      <td width="168" align="center" valign="top">
        <span class="style35">{{text3}}</span>
      </td>
      <td valign="top">&nbsp;</td>
    </tr>
    <tr>
      <td height="118" valign="top">&nbsp;</td>
      <td valign="top">&nbsp;</td>
      <td valign="top">&nbsp;</td>
    </tr>
  </table>
  
</template>
<script>
export default {
  props: {
    text5a: String,
    anata: String,
    text5b: String,
    text3: String
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
}
</style>
