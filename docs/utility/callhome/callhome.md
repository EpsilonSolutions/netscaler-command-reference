#callhome

The following operations can be performed on "callhome":


[show](#show-callhome) | [set](#set-callhome) | [unset](#unset-callhome)

##show callhome

Displays the CallHome configuration and trigger event details.


##Synopsys

show callhome 


##Outputs

<b>emailAddress</b>
Email address of the contact administrator.

<b>hbCustomInterval</b>
Interval (in days) between CallHome heartbeats

<b>proxyMode</b>
Enables or disables the proxy mode. The proxy server can be set by either specifying the IP address of the server or the name of the service representing the proxy server.

<b>IPAddress</b>
IP address of the proxy server.

<b>port</b>
HTTP port on the Proxy server. This is a mandatory parameter for both IP address and service name based configuration.

<b>proxyAuthService</b>
Name of the service that represents the proxy server.

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

<b>RLfirstHighDrop</b>
First occurence of high rate limit drops

<b>RLlatestHighDrop</b>
Latest occurence of high rate limit drops

<b>restartLatestfail</b>
Latest occurrence warm restart failure.

<b>memthreFirstAnomaly</b>
First occurrence of memory anomaly.

<b>memthreLatestAnomaly</b>
Latest occurrence of memory anomaly.

<b>callhomestatus</b>
Callhome feature enabled/disable, register with upload server successful/failed



##Example

 show callhome	E-mail address configured:xxx@yahoo.com        Heartbeat Custom Interval(days): 20Trigger event	             State    First occurrence              Latest occurrence -------------                -----    ----------------              -----------------1) Compact flash errors      Enabled  ..							..2) Hard disk drive errors	 Enabled  ..							..3) Power supply unit failure Enabled  27 Aug 2010 18:22:47      	28 Aug 2010 18:22:47       4) SSL card failure          Enabled  25 Aug 2010 18:22:47      	26 Aug 2010 18:22:47       5) Warm restart			     Enabled  N/A						 	..                                     

##set callhome

Sets CallHome parameters


##Synopsys

set callhome [-emailAddress &lt;string>] [-proxyMode ( YES | NO )] [-IPAddress &lt;ip_addr|ipv6_addr|*> | -proxyAuthService &lt;string>] [-port &lt;port|*>] [-hbCustomInterval &lt;number of days>]


##Arguments

<b>emailAddress</b>
Email address of the contact administrator.

<b>hbCustomInterval</b>
Interval (in days) between CallHome heartbeats
Minimum value: 1
Maximum value: 30

<b>proxyMode</b>
Enables or disables the proxy mode. The proxy server can be set by either specifying the IP address of the server or the name of the service representing the proxy server.
Possible values: YES, NO
Default value: NO

<b>IPAddress</b>
IP address of the proxy server.

<b>proxyAuthService</b>
Name of the service that represents the proxy server.

<b>port</b>
HTTP port on the Proxy server. This is a mandatory parameter for both IP address and service name based configuration.
Minimum value: 1



##Example

set callhome -emailAddress abc@xyz.com -proxyMode YES -proxyauthService callhome_proxy -port 80 -hbCustomInterval 6

##unset callhome

Use this command to remove  callhome settings.Refer to the set  callhome command for meanings of the arguments.


##Synopsys

unset callhome [-emailAddress] [-hbCustomInterval] [-proxyMode] [-IPAddress] [-proxyAuthService] [-port]


