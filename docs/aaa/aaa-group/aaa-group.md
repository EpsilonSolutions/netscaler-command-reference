#aaa group

The following operations can be performed on "aaa group":


[add](#add-aaa-group) | [rm](#rm-aaa-group) | [bind](#bind-aaa-group) | [unbind](#unbind-aaa-group) | [show](#show-aaa-group)

##add aaa group

Creates a AAA group and verifies the configuration to ensure that it is correct.


##Synopsys

add aaa group &lt;groupName>


##Arguments

<b>groupName</b>
Name for the group. Must begin with a letter, number, or the underscore character (_), and must consist only of letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore  characters. Cannot be changed after the group is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or
single quotation marks (for example, ?my aaa group? or ?my aaa
	group).



##Example

add aaa group group_ad

##rm aaa group

Removes the specified AAA group.


##Synopsys

rm aaa group &lt;groupName>


##Arguments

<b>groupName</b>
Name of the group that you are removing.



##bind aaa group

Binds the specified AAA group to the specified resource. The resource can be a user, an Intranet IP address or range, a policy, or an Intranet application.


##Synopsys

bind aaa group &lt;groupName> [-userName &lt;string>] [-policy &lt;string>  [-priority &lt;positive_integer>]] [-intranetApplication &lt;string>] [-urlName &lt;string>] [-intranetIP &lt;ip_addr>  &lt;netmask>] [-intranetIP6 &lt;ip_addr|ipv6_addr|*>  &lt;numaddr>]


##Arguments

<b>groupName</b>
Name of the group that you are binding.

<b>userName</b>
Bind a AAA group to the specified AAA user.
If the specified user is bound to more than one group, the group expressions are evaluated, upon authorization, to determine the appropriate action.

<b>policy</b>
Bind a policy to the specified AAA group.

<b>priority</b>
Priority to assign to the policy, as an integer. A lower number indicates a higher priority.  
Required when binding a group to a policy. Not relevant to any other
type of group binding.
Minimum value: 0

<b>intranetApplication</b>
Bind the group to the specified intranet VPN application.

<b>urlName</b>
Bind the group to the specified URL.

<b>intranetIP</b>
Bind the group to the specified IP address or IP block. 
Normally you would bind the group to an IP address or range that your users use to access intranet resources.

<b>netmask</b>
Subnet mask specifying an IP-address range to which to bind a AAA group.

<b>intranetIP6</b>
Bind the group to the specified IP6 address or IP block. 
Normally you would bind the group to an IP6 address or range that your users use to access intranet resources.

<b>numaddr</b>
Number of ipv6 address to be bound
Minimum value: 1



##Example

To bind an Intranet IP to the group engg:	bind aaa group engg  -intranetip 10.102.10.0 255.255.255.0

##unbind aaa group

Unbinds the specified AAA group from the specified resource. The resource can be a user, an intranet IP address or range, a policy, or an intranet application.


##Synopsys

unbind aaa group &lt;groupName> [-userName &lt;string> ...] [-policy &lt;string>] [-intranetApplication &lt;string>] [-urlName &lt;string>] [-intranetIP &lt;ip_addr>  &lt;netmask>] [-intranetIP6 &lt;ip_addr|ipv6_addr|*>  [&lt;numaddr>]]


##Arguments

<b>groupName</b>
Name of the group that you are unbinding.

<b>userName</b>
Unbind the specified AAA group from the specified AAA user.

<b>policy</b>
Unbind the specified policy from the specified AAA group.

<b>intranetApplication</b>
Unbind the specified group from the specified intranet VPN application.

<b>urlName</b>
Unbind the specified group from the specified URL.

<b>intranetIP</b>
Unbind the specified group from the specified IP address or IP block.

<b>netmask</b>
Subnet mask for the IP range in which the intranet application from which you are unbinding the policy resides. 
Required if the intranet application has multiple IP addresses bound to it. Not needed if the intranet application resides on a single IP address.

<b>intranetIP6</b>
IP6 address of the intranet application to which you are unbinding the policy.

<b>numaddr</b>
Number of addresses for the IPv6 range in which the intranet application to which you are binding the policy resides. 
Required if the intranet application has multiple IPv6 addresses bound to
it. Not needed if the intranet application resides on a single IP
address.
Minimum value: 1



##Example

 unbind aaa group engg -intranetip 10.102.10.0 255.255.255.0

##show aaa group

Displays the current configuration of a AAA group.


##Synopsys

show aaa group [&lt;groupName>] [-loggedIn]


##Arguments

<b>groupName</b>
Name of the group.

<b>loggedIn</b>
Display only the group members who are currently logged in.



##Outputs

<b>userName</b>
The user name.

<b>policy</b>
The policy name.

<b>priority</b>
Priority to assign to the policy, as an integer. A lower number indicates a higher priority.  
Required when binding a group to a policy. Not relevant to any other
type of group binding.

<b>intranetApplication</b>
Bind the group to the specified intranet VPN application.

<b>urlName</b>
The intranet url

<b>actType</b>

<b>intranetIP</b>
The Intranet IP(s) bound to the group

<b>netmask</b>
The netmask for the Intranet IP

<b>intranetIP6</b>
The Intranet IP6(s) bound to the group

<b>numaddr</b>
Numbers of ipv6 address bound starting with intranetip6

<b>policySubType</b>

<b>stateflag</b>

<b>devno</b>

<b>count</b>



##Example

&gt; show aaa group engg        GroupName: engg        Bound AAA users:        UserName: joe        UserName: jane        Intranetip IP: 10.102.10.0      Netmask: 255.255.255.0 Done&gt;

