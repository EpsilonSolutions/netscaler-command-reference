#aaa group

The following operations can be performed on "aaa group":


[add](#add-aaa-group) | [rm](#rm-aaa-group) | [bind](#bind-aaa-group) | [unbind](#unbind-aaa-group) | [show](#show-aaa-group)

##add aaa group

Creates a AAA group and verifies the configuration to ensure that it is correct.


##Synopsys

add aaa group &lt;groupName> [-weight &lt;positive_integer>]


##Arguments

<b>groupName</b>
Name for the group. Must begin with a letter, number, or the underscore character (_), and must consist only of letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore  characters. Cannot be changed after the group is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or
single quotation marks (for example, "my aaa group" or 'my aaa group').

<b>weight</b>
Weight of this group with respect to other configured aaa groups (lower the number higher the weight)
Default value: 0
Minimum value: 0
Maximum value: 65535



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

bind aaa group &lt;groupName> [-userName &lt;string>] [-policy &lt;string>  [-priority &lt;positive_integer>]  [-gotoPriorityExpression &lt;expression>]] [-intranetApplication &lt;string>] [-urlName &lt;string>] [-intranetIP &lt;ip_addr>  &lt;netmask>] [-intranetIP6 &lt;ip_addr|ipv6_addr|*>  &lt;numaddr>]


##Arguments

<b>groupName</b>
Name of the group that you are binding.

<b>userName</b>
Bind a AAA group to the specified AAA user.
If the specified user is bound to more than one group, the group expressions are evaluated, upon authorization, to determine the appropriate action.

<b>policy</b>
Bind a policy to the specified AAA group.

<b>priority</b>
Integer specifying the priority of the policy. A lower number indicates a higher priority. Policies are evaluated in the order of their priority numbers. Maximum value for default syntax policies is 2147483647 and for classic policies is 64000.
Minimum value: 0
Maximum value: 2147483647

<b>intranetApplication</b>
Bind the group to the specified intranet VPN application.

<b>urlName</b>
Bind the group to the specified URL.

<b>intranetIP</b>
Bind the group to the specified IP address or IP block. 
Normally you would bind the group to an IP address or range that your users use to access intranet resources.

<b>netmask</b>
Subnet mask specifying an IP-address range to which to bind a AAA group.

<b>gotoPriorityExpression</b>
Expression or other value specifying the next policy to evaluate if the current policy evaluates to TRUE.  Specify one of the following values:
* NEXT - Evaluate the policy with the next higher priority number.
* END - End policy evaluation.
* USE_INVOCATION_RESULT - Applicable if this policy invokes another policy label. If the final goto in the invoked policy label has a value of END, the evaluation stops. If the final goto is anything other than END, the current policy label performs a NEXT.
* A default syntax or classic expression that evaluates to a number.
If you specify an expression, the number to which it evaluates determines the next policy to evaluate, as follows:
*  If the expression evaluates to a higher numbered priority, the policy with that priority is evaluated next.
* If the expression evaluates to the priority of the current policy, the policy with the next higher numbered priority is evaluated next.
* If the expression evaluates to a number that is larger than the largest numbered priority, policy evaluation ends.
An UNDEF event is triggered if:
* The expression is invalid.
* The expression evaluates to a priority number that is numerically lower than the current policy's priority.
* The expression evaluates to a priority number that is between the current policy's priority number (say, 30) and the highest priority number (say, 100), but does not match any configured priority number (for example, the expression evaluates to the number 85). This example assumes that the priority number increments by 10 for every successive policy, and therefore a priority number of 85 does not exist in the policy label.

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

show aaa group [&lt;groupName>] [-loggedIn] [-weight &lt;positive_integer>]


##Arguments

<b>groupName</b>
Name of the group.

<b>loggedIn</b>
Display only the group members who are currently logged in.

<b>weight</b>
Weight of this group with respect to other configured aaa groups (lower the number higher the weight)
Default value: 0
Minimum value: 0
Maximum value: 65535



##Outputs

<b>userName</b>
The user name.

<b>policy</b>
The policy name.

<b>priority</b>
Integer specifying the priority of the policy. A lower number indicates a higher priority. Policies are evaluated in the order of their priority numbers. Maximum value for default syntax policies is 2147483647 and for classic policies is 64000.

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

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>devno</b>

<b>count</b>



##Example

&gt; show aaa group engg        GroupName: engg        Bound AAA users:        UserName: joe        UserName: jane        Intranetip IP: 10.102.10.0      Netmask: 255.255.255.0 Done&gt;

