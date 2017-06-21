#dns action

The following operations can be performed on "dns action":


[add](#add-dns-action) | [rm](#rm-dns-action) | [set](#set-dns-action) | [unset](#unset-dns-action) | [show](#show-dns-action)

##add dns action

Add a dns action.


##Synopsys

add dns action &lt;actionName> &lt;actionType> [-IPAddress &lt;ip_addr|ipv6_addr> ... | -viewName &lt;string> | -preferredLocList &lt;string> ...] [-TTL &lt;secs>] [-dnsProfileName &lt;string>]


##Arguments

<b>actionName</b>
Name of the dns action.

<b>actionType</b>
The type of DNS action that is being configured.
Possible values: ViewName, GslbPrefLoc, noop, Drop, Cache_Bypass, Rewrite_Response

<b>IPAddress</b>
List of IP address to be returned in case of rewrite_response actiontype. They can be of IPV4 or IPV6 type.
	    In case of set command We will remove all the IP address previously present in the action and will add new once given in set dns action command.

<b>TTL</b>
Time to live, in seconds.
Default value: 3600
Maximum value: 2147483647

<b>viewName</b>
The view name that must be used for the given action.

<b>preferredLocList</b>
The location list in priority order used for the given action.

<b>dnsProfileName</b>
Name of the DNS profile to be associated with the transaction for which the action is chosen



##Example

add dns action &lt;actionName&gt; &lt;actionType&gt; (-IPAddress &lt;ip_addr|ipv6_addr&gt; ... | -viewName &lt;string&gt; | -preferredLocList &lt;string&gt; ...) [-TTL &lt;secs&gt;]add dns action action1  Rewrite_Response -ipAddress 10.102.27.153 10.102.27.154 33::33 44::44 -TTL 4000add dns action action1  GslbPrefLoc -preferredLocList india.10.102.81.175.80 us.10.102.81.176.80add dns action action1  ViewName -viewName dnsview1 

##rm dns action

Removes a dns Action.


##Synopsys

rm dns action &lt;actionName>


##Arguments

<b>actionName</b>
Name of the dns action.



##Example

rm dns action action1

##set dns action

Set a dns Action. Use this command to set the values for Ip address and TTL, If Ipaddress is given in set dns action command we will discard the previous set and will apply this new set of ipaddress given.


##Synopsys

set dns action &lt;actionName> [-IPAddress &lt;ip_addr|ipv6_addr> ...] [-TTL &lt;secs>] [-viewName &lt;string>] [-preferredLocList &lt;string> ...] [-dnsProfileName &lt;string>]


##Arguments

<b>actionName</b>
Name of the dns action.

<b>IPAddress</b>
List of IP address to be returned in case of rewrite_response actiontype. They can be of IPV4 or IPV6 type.
	    In case of set command We will remove all the IP address previously present in the action and will add new once given in set dns action command.

<b>TTL</b>
Time to live, in seconds.
Default value: 3600
Maximum value: 2147483647

<b>viewName</b>
The view name that must be used for the given action.

<b>preferredLocList</b>
The location list in priority order used for the given action.

<b>dnsProfileName</b>
Name of the DNS profile to be associated with the transaction for which the action is chosen



##Example

set dns action &lt;actionName&gt; [-IPAddress &lt;ip_addr|ipv6_addr&gt; ...] [-TTL &lt;secs&gt;] [-viewName &lt;string&gt;] [-preferredLocList &lt;string&gt; ...]set dns action action1  -ipAddress 10.102.27.153 10.102.27.154 33::33 44::44 -TTL 4000set dns action action1 	-viewName dnsview2set dns action action1  -preferredLocList india.10.102.81.175.80

##unset dns action

Use this command to remove dns action settings.Refer to the set dns action command for meanings of the arguments.


##Synopsys

unset dns action &lt;actionName> [-TTL] [-dnsProfileName]


##show dns action

Used to display the action-related information.


##Synopsys

show dns action [&lt;actionName>]


##Arguments

<b>actionName</b>
Name of the dns action.



##Outputs

<b>actionType</b>
The type of DNS action that is being configured.

<b>TTL</b>
Time to live, in seconds.

<b>IPAddress</b>
List of IP address to be returned in case of rewrite_response actiontype. They can be of IPV4 or IPV6 type.
	    In case of set command We will remove all the IP address previously present in the action and will add new once given in set dns action command.

<b>viewName</b>
The view name that must be used for the given action.

<b>preferredLocList</b>
The location list in priority order used for the given action.

<b>drop</b>
The dns packet must be dropped.

<b>cacheBypass</b>
By pass dns cache for this.

<b>dnsProfileName</b>
Name of the DNS profile to be associated with the transaction for which the action is chosen

<b>builtin</b>
Flag to determine whether DNS action is default or not

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show dns action &lt;Action-Name&gt;show dns action action1show dns action

