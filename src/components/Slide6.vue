<template>
  
    <table
      width="540"
      border="0"
      cellpadding="0"
      cellspacing="0"
      background="http://portal.nifty.com/2010/02/28/b/img/006.gif"
      class="slide"
    >
      <tr>
        <td width="10" valign="top">&nbsp;</td>
        <td width="120" valign="top">&nbsp;</td>
        <td width="163" valign="top">&nbsp;</td>
        <td width="136" height="82" align="center" valign="bottom">&nbsp;</td>
        <td width="111" valign="top">&nbsp;</td>
      </tr>
      <tr>
        <td valign="top">&nbsp;</td>
        <td valign="top">&nbsp;</td>
        <td valign="top">&nbsp;</td>
        <td height="49" align="center" valign="middle" class="style25">{{text8}}</td>
        <td valign="top">&nbsp;</td>
      </tr>
      <tr>
        <td valign="top">&nbsp;</td>
        <td align="right" valign="bottom" nowrap class="style20">{{aite}}</td>
        <td valign="bottom">
          <span class="style20">様</span>
        </td>
        <td height="46" align="center" valign="bottom">&nbsp;</td>
        <td valign="top">&nbsp;</td>
      </tr>
      <tr>
        <td valign="top">&nbsp;</td>
        <td valign="top">&nbsp;</td>
        <td valign="top">&nbsp;</td>
        <td height="60" align="center" valign="middle" class="style25">{{text3}}</td>
        <td valign="top">&nbsp;</td>
      </tr>
      <tr>
        <td valign="top">&nbsp;</td>
        <td align="right" valign="middle" nowrap class="style20">{{anata}}</td>
        <td valign="top">&nbsp;</td>
        <td height="50" align="center" valign="bottom">&nbsp;</td>
        <td valign="top">&nbsp;</td>
      </tr>
      <tr>
        <td valign="top">&nbsp;</td>
        <td valign="top">&nbsp;</td>
        <td valign="top">&nbsp;</td>
        <td height="118" align="center" valign="bottom">&nbsp;</td>
        <td valign="top">&nbsp;</td>
      </tr>
    </table>

</template>

<script>
export default {
  props: {
    text8: String,
    aite: String,
    text3: String,
    anata: String
  }
};
</script>

<style scoped>
.style25 {
    font-size: 25px;
    font-weight: 400;
    line-height: 130%;
}
.style20 {
    font-size: 20px;
    font-weight: 400;
    line-height: 150%;
}
table {
  margin-bottom: 20px;
}
</style>