#reputation settings

The following operations can be performed on "reputation settings":


[set](#set-reputation-settings) | [unset](#unset-reputation-settings) | [show](#show-reputation-settings)

##set reputation settings

Sets the reputation service engine settings.


##Synopsys

set reputation settings [-proxyServer &lt;string>] [-proxyPort &lt;positive_integer>]


##Arguments

<b>proxyServer</b>
Proxy server IP to get Reputation data.
Default value: NS_S_REPUTATION_PROXY_SERVER_DEFAULT

<b>proxyPort</b>
Proxy server port.
Minimum value: 0



##unset reputation settings

Use this command to remove reputation settings settings.Refer to the set reputation settings command for meanings of the arguments.


##Synopsys

unset reputation settings [-proxyServer] [-proxyPort]


##show reputation settings

Displays the reputation service engine settings.


##Synopsys

show reputation settings


##Outputs

<b>proxyServer</b>
Proxy server IP to get Reputation data.

<b>proxyPort</b>
Proxy server port.



