#callhome

The following operations can be performed on "callhome":


[show](#show-callhome) | [set](#set-callhome) | [unset](#unset-callhome)

##show callhome

Displays the trigger events configured and the time when these events were triggered. 


##Synopsys

show callhome 


##Outputs

<b>emailAddress</b>
The contact person's E-mail address.

<b>proxyMode</b>
Deploy the callhome proxy mode

<b>IPAddress</b>
Proxy Server IP address

<b>port</b>
Proxy Server Port

<b>sslcardfirstfailure</b>
First occurrence SSL card failure.

<b>sslcardlatestfailure</b>
Latest occurrence SSL card failure.

<b>powfirstfail</b>
First occurrence power supply unit failure.

<b>powlatestfailure</b>
Latest occurrence power supply unit failure.

<b>HDDfirstfail</b>
First occurrence hard disk drive failure.

<b>HDDlatestfailure</b>
Latest occurrence hard disk drive failure.

<b>FLASHfirstfail</b>
First occurrence compact flash failure.

<b>FLASHlatestfailure</b>
Latest occurrence compact flush failure.

<b>restartLatestfail</b>
Latest occurrence warm restart failure.

<b>callhomestatus</b>
Callhome feature enabled/disable, register with upload server successful/failed



##Example

 show callhome	E-mail address configured:xxx@yahoo.comTrigger event	             State    First occurrence              Latest occurrence -------------                -----    ----------------              -----------------1) Compact flash errors      Enabled  ..							..2) Hard disk drive errors	 Enabled  ..							..3) Power supply unit failure Enabled  27 Aug 2010 18:22:47      	28 Aug 2010 18:22:47       4) SSL card failure          Enabled  25 Aug 2010 18:22:47      	26 Aug 2010 18:22:47       5) Warm restart			     Enabled  N/A						 	..                                     

##set callhome

Sets the contact person's E-mail address


##Synopsys

set callhome -emailAddress e-mailaddress 


##Arguments

<b>emailAddress</b>
The contact person's E-mail address.

<b>proxyMode</b>
Deploy the callhome proxy mode
Possible values: YES, NO
Default value: NO

<b>IPAddress</b>
Proxy Server IP address

<b>port</b>
Proxy Server Port
Minimum value: 1



##Example

set callhome -emailAddress xxxx@yahoo.com

##unset callhome

Use this command to remove  callhome settings.Refer to the set  callhome command for meanings of the arguments.


##Synopsys

unset callhome [-emailAddress] [-proxyMode] [-IPAddress] [-port]


