<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=gb2312" />
<title>D3装备对比工具</title>
<style>
input {
  border-top-color: #000000;
	border-right-color: #000000;
	border-bottom-color: #000000;
	border-left-color: #000000;
	border-top-width: 1px;
	border-right-width: 1px;
	border-bottom-width: 1px;
	border-left-width: 1px;
	padding: 2px;
}
</style>
<script>function $(id){return document.getElementById(id);}</script>
</head>
<body>
<table width="90%" border="0" align="center" cellpadding="5" cellspacing="1" bgcolor="#0033CC">
  <tr>
    <td colspan="26" bgcolor="#FFFFFF"><table width="100%" border="0" cellpadding="5" cellspacing="0">
  <tr>
    <td>职业<input id="occupation" type="hidden" value="1" />
      <input name="o1" id="o11" type="radio" value="1" checked="checked" onclick="$('occupation').value=this.value;"/>
野蛮人
<input name="o1" id="o12" type="radio" value="2" onclick="$('occupation').value=this.value;"/>
武僧
<input name="o1" id="o13" type="radio" value="2" onclick="$('occupation').value=this.value;"/>
恶魔猎手
<input name="o1" id="o14" type="radio" value="3" onclick="$('occupation').value=this.value;"/>
巫医
<input name="o1" id="o15" type="radio" value="3" onclick="$('occupation').value=this.value;"/>
秘术师</td>
    <td></td>
    <td align="right">怪物等级(mlvl)
      <input name="mlvl" type="text" id="mlvl" value="60" size="4" maxlength="3" />  炼狱1/2/3/4-61/62/63/63</td>
  </tr>
</table></td>
  </tr>
  <tr>
    <td colspan="26" bgcolor="#FFFFFF"><table width="100%" border="0" cellpadding="5" cellspacing="0">
      <tr>
        <td width="80" valign="top" nowrap="nowrap">使用说明：</td>
        <td>1.伤害是根据武器伤害X（1+主属性/100）来计算的，没有像面板中那种来衡量，毕竟技能伤害是根据武器伤害来衡量的，攻速尤其是在103被砍之后有些浮云了。<br />
          2.需要导出数据的把数据填好以后点击导出，鼠标放到前边的文本框上按Ctrl+C或者点鼠标右键来选‘复制’来复制数据<br />
          3.需要导入数据的时候把数据复制到文本框中点击导入就可以了<br />
          4.之所以选择使用html，就是考虑到方便大家在线使用，不需要其他的软件的支持；鉴于现在网站备案的问题，就不挂在我自己的网站上了。<br />
          5.有什么问题和意见可以联系我 gallop2k@163.com battleTag: ripper#3124 美服，首发凯恩之角，转载请注明出处</td>
      </tr>
    </table></td>
  </tr>
  <tr>
    <td colspan="13" bgcolor="#FFFFFF"><table width="100%" border="0" cellpadding="5" cellspacing="0">
      <tr>
        <td width="80" nowrap="nowrap">普通伤害：</td>
        <td id="damage1">&nbsp;</td>
        <td align="right">100%武器伤害</td>
      </tr>
    </table></td>
    <td colspan="13" bgcolor="#FFFFFF"><table width="100%" border="0" cellpadding="5" cellspacing="0">
      <tr>
        <td width="80" nowrap="nowrap">普通伤害：</td>
        <td id="damage2">&nbsp;</td>
        <td align="right">100%武器伤害</td>
      </tr>
    </table></td>
  </tr>
  <tr>
    <td colspan="13" bgcolor="#FFFFFF"><table width="100%" border="0" cellpadding="5" cellspacing="0">
      <tr>
        <td width="80" nowrap="nowrap">暴击伤害：</td>
        <td id="cdamage1">&nbsp;</td>
        <td align="right">人物50%+装备</td>
      </tr>
    </table></td>
    <td colspan="13" bgcolor="#FFFFFF"><table width="100%" border="0" cellpadding="5" cellspacing="0">
      <tr>
        <td width="80" nowrap="nowrap">暴击伤害：</td>
        <td id="cdamage2">&nbsp;</td>
        <td align="right">人物50%+装备</td>
      </tr>
    </table></td>
  </tr>
  <tr>
    <td colspan="13" bgcolor="#FFFFFF"><table width="100%" border="0" cellpadding="5" cellspacing="0">
      <tr>
        <td width="80" nowrap="nowrap">护甲减免：</td>
        <td id="armor1">&nbsp;</td>
        <td align="right">护甲值/(护甲值+mlvl*50)</td>
      </tr>
    </table></td>
    <td colspan="13" bgcolor="#FFFFFF"><table width="100%" border="0" cellpadding="5" cellspacing="0">
      <tr>
        <td width="80" nowrap="nowrap">护甲减免：</td>
        <td id="armor2">&nbsp;</td>
        <td align="right">护甲值/(护甲值+mlvl*50)</td>
      </tr>
    </table></td>
  </tr>
  <tr>
    <td colspan="13" bgcolor="#FFFFFF"><table width="100%" border="0" cellpadding="5" cellspacing="0">
      <tr>
        <td width="80" nowrap="nowrap">抗性减免：</td>
        <td id="resist1">&nbsp;</td>
        <td align="right">抗性/(抗性+mlvl*5)</td>
      </tr>
    </table></td>
    <td colspan="13" bgcolor="#FFFFFF"><table width="100%" border="0" cellpadding="5" cellspacing="0">
      <tr>
        <td width="80" nowrap="nowrap">抗性减免：</td>
        <td id="resist2">&nbsp;</td>
        <td align="right">抗性/(抗性+mlvl*5)</td>
      </tr>
    </table></td>
  </tr>
  <tr>
    <td colspan="13" bgcolor="#FFFFFF"><table width="100%" border="0" cellpadding="5" cellspacing="0">
      <tr>
        <td width="80" nowrap="nowrap">综合减免：</td>
        <td id="all1">&nbsp;</td>
        <td align="right">护甲减免*抗性减免*人物减免</td>
      </tr>
    </table></td>
    <td colspan="13" bgcolor="#FFFFFF"><table width="100%" border="0" cellpadding="5" cellspacing="0">
      <tr>
        <td width="80" nowrap="nowrap">综合减免：</td>
        <td id="all2">&nbsp;</td>
        <td align="right">护甲减免*抗性减免*人物减免</td>
      </tr>
    </table></td>
  </tr>
  <tr>
    <td colspan="13" bgcolor="#FFFFFF"><table width="100%" border="0" cellpadding="5" cellspacing="0">
      <tr>
        <td width="80" nowrap="nowrap">遭受伤害：</td>
        <td id="left1">&nbsp;</td>
        <td align="right">100K来自怪物伤害减免后</td>
      </tr>
    </table></td>
    <td colspan="13" bgcolor="#FFFFFF"><table width="100%" border="0" cellpadding="5" cellspacing="0">
      <tr>
        <td width="80" nowrap="nowrap">遭受伤害：</td>
        <td id="left2">&nbsp;</td>
        <td align="right">100K来自怪物伤害减免后</td>
      </tr>
    </table></td>
  </tr>
  <tr>
    <td colspan="13" bgcolor="#FFFFFF">&nbsp;套装一
      <input name="data1" type="text" id="data1" size="70" onmouseover="this.select()" onselect="this.focus()"/>
      <input type="button" value="导入" onclick="importdata('1')"/>
      <input type="button" value="导出" onclick="exportdata('1')"/>
      <input type="button" onclick="calcdata('1')" value="计算结果"/></td>
    <td colspan="13" bgcolor="#FFFFFF">&nbsp;套装二
      <input name="data2" type="text" id="data2" size="70" />
      <input type="button" value="导入" onclick="importdata('2')"/>
      <input type="button" value="导出" onclick="exportdata('2')" />
      <input type="button" onclick="calcdata('2')" value="计算结果"/></td>
  </tr>
  <tr>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">装备类型</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">力量</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">敏捷</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">智力</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">体能</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">护甲值</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">全抗性</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">最小伤害</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">最大伤害</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">暴击几率</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">暴击伤害</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">攻速</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">生命%</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">装备类型</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">力量</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">敏捷</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">智力</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">体能</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">护甲值</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">全抗性</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">最小伤害</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">最大伤害</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">暴击几率</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">暴击伤害</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">攻速</td>
    <td align="center" nowrap="nowrap" bgcolor="#FFFFFF">生命%</td>
  </tr>
  <tr>
    <td align="center" bgcolor="#FFFFFF">综合统计</td>
    <td align="center" bgcolor="#FFFFFF" id="p11">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF" id="p12">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF" id="p13">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF" id="p14">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF" id="p15">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF" id="p16">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF" id="p17">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF" id="p18">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF" id="p19">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF" id="p110">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF" id="p111">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF" id="p112">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF">综合统计</td>
    <td align="center" bgcolor="#FFFFFF" id="p21">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF" id="p22">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF" id="p23">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF" id="p24">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF" id="p25">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF" id="p26">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF" id="p27">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF" id="p28">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF" id="p29">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF" id="p210">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF" id="p211">&nbsp;</td>
    <td align="center" bgcolor="#FFFFFF" id="p212">&nbsp;</td>
  </tr>
<tbody id="itemsDisplay"/>
</table>
<br />
<script>
var	itemName = [['头盔','1','1','1','1', '1','1', '0','0', '0','0','0', '1'],
				['护肩','1','1','1','1', '1','1', '0','0', '0','0','0', '1'],
				['护腕','1','1','1','1', '1','1', '0','0', '0','0','0', '0'],
				['胸甲','1','1','1','1', '1','1', '0','0', '0','0','0', '1'],
				['腰带','1','1','1','1', '1','1', '0','0', '0','0','0', '1'],
				['裤子','1','1','1','1', '1','1', '0','0', '0','0','0', '0'],
				['鞋子','1','1','1','1', '1','1', '0','0', '0','0','0', '0'],
				['手套','1','1','1','1', '1','1', '0','0', '1','1','1', '0'],
			  ['护身符','1','1','1','1', '1','1', '1','1', '1','1','1', '1'],
			   ['戒指1','1','1','1','1', '1','1', '1','1', '1','1','1', '1'],
			   ['戒指2','1','1','1','1', '1','1', '1','1', '1','1','1', '1'],
				['武器','1','1','1','1', '1','1', '1','1', '0','1','1', '1'],
				['副手','1','1','1','1', '1','1', '1','1', '1','0','1', '1']];

function displayItems(){
	/*clear*/
	tbodyObj = $("itemsDisplay");
	while (tbodyObj.hasChildNodes()) {tbodyObj.removeChild(tbodyObj.firstChild);}
	/*init */
	
	for(i=0;i<itemName.length;i++){
		
		lineRow = document.createElement("tr");
		lineRow.id = "tr" + i;
		lineRow.bgColor = '#ffffff';
		lineRow.align = 'center';
		
		lineCell = document.createElement("td");
		lineCell.innerHTML = itemName[i][0];
		lineRow.appendChild(lineCell);
		
		for(j=1;j<13;j++){
			lineCell = document.createElement("td");
			lineCell.innerHTML = '<input type='+(itemName[i][j]=='1'?'text':'hidden')+' id=xp1'+i+j+' size=4 maxlength=4>';
			lineRow.appendChild(lineCell);
		}
		
		lineCell = document.createElement("td");
		lineCell.innerHTML = itemName[i][0];
		lineRow.appendChild(lineCell);
		
		for(j=1;j<13;j++){
			lineCell = document.createElement("td");
			lineCell.innerHTML = '<input type='+(itemName[i][j]=='1'?'text':'hidden')+' id=xp2'+i+j+' size=4 maxlength=4>';
			lineRow.appendChild(lineCell);
		}	
		tbodyObj.appendChild(lineRow);
	}	
}

function exportdata(v1){
	var sdata = 'item';
	for(i=0;i<13;i++){
		for(j=1;j<13;j++){
			sdata += ','+ $('xp'+v1+i+j).value;
		}
	}
	$('data'+v1).value = sdata;
}

function importdata(v1){
	var sdata = $('data'+v1).value.split(',');
	for(i=0;i<13;i++){
		for(j=1;j<13;j++){
			$('xp'+v1+i+j).value = sdata[i*12+j];
		}
	}
	calcdata(v1);
}
function calcdata(v1){
	for(j=1;j<13;j++){
		var t = 0;
		for(i=0;i<13;i++){
			t += Number($('xp'+v1+i+j).value);
		}
		$('p'+v1+j).innerHTML = t;
	}
	m_attr = 100 + $('p'+v1+$('occupation').value).innerHTML;
	//普通伤害
	$('damage'+v1).innerHTML = ($('p'+v1+7).innerHTML * m_attr / 100) + "--" + ($('p'+v1+8).innerHTML * m_attr / 100);
	//暴击伤害
	$('cdamage'+v1).innerHTML = ($('p'+v1+7).innerHTML * m_attr / 100 * (1.5+$('p'+v1+10).innerHTML/100)) + "--" + ($('p'+v1+8).innerHTML * m_attr / 100 * (1.5+$('p'+v1+10).innerHTML/100));
	//护甲减免
	var d_armor = $('p'+v1+5).innerHTML/(Number($('p'+v1+5).innerHTML)+Number($('mlvl').value*50));
	$('armor'+v1).innerHTML = (d_armor * 100).toFixed(2) +'%';
	//抗性减免
	var d_resist = $('p'+v1+6).innerHTML/(Number($('p'+v1+6).innerHTML)+Number($('mlvl').value*5))
	$('resist'+v1).innerHTML = (d_resist * 100).toFixed(2) +'%';
	//综合减免
	var d_all = 1-(1-d_armor)*(1-d_resist)*($('o11').checked||$('o12').checked?0.7:1)
	$('all'+v1).innerHTML = (d_all * 100).toFixed(2) +'%';
	//遭受伤害
	$('left'+v1).innerHTML = Math.round(100000*(1-d_all));
}


displayItems();
</script>
</body>
</html>
