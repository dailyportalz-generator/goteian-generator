<template>

  <table width="540" border="0" cellpadding="0" cellspacing="0" background="http://portal.nifty.com/2010/02/28/b/img/004.gif" class="slide">
    <tr>
      <td width="50" valign="top">&nbsp;</td>
      <td height="150" colspan="3" align="center" valign="bottom"><span class="style25">{{text6}}</span></td>
      <td width="47" valign="top">&nbsp;</td>
    </tr>
    <tr>
      <td height="20" valign="top">&nbsp;</td>
      <td colspan="3"  valign="top">&nbsp;</td>
      <td valign="top">&nbsp;</td>
    </tr>
    <tr>
      <td height="40" valign="top">&nbsp;</td>
      <td width="234"  valign="top">&nbsp;</td>
      <td width="158" align="center"  valign="top" class="style25">{{anata}}</td>
      <td width="51"  valign="top">&nbsp;</td>
      <td valign="top">&nbsp;</td>
    </tr>
    <tr>
      <td height="195" valign="top">&nbsp;</td>
      <td colspan="3"  valign="top">&nbsp;</td>
      <td valign="top">&nbsp;</td>
    </tr>
  </table>

</template>
<script>
export default {
  props: {
    anata: String,
    text6: String,
  },
};
</script>
<style scoped>
.style25 {
    font-size: 25px;
    font-weight: 400;
    line-height: 130%;
}
table {
  margin-bottom: 20px;
}
</style>