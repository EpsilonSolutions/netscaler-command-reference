#aaa certParams

The following operations can be performed on "aaa certParams":


[set](#set-aaa-certparams) | [unset](#unset-aaa-certparams) | [show](#show-aaa-certparams)

##set aaa certParams

Modifies the global configuration settings for certificate policies. The settings that you specify are used for all SSL-VPN virtual servers unless you use authentication policies to create a configuration for a specific SSL-VPN virtual server.


##Synopsys

set aaa certParams [-userNameField &lt;string>] [-groupNameField &lt;string>] [-defaultAuthenticationGroup &lt;string>]


##Arguments

<b>userNameField</b>
Client certificate field that contains the username, in the format &lt;field&gt;:&lt;subfield&gt;.

<b>groupNameField</b>
Client certificate field that specifies the group, in the format &lt;field&gt;:&lt;subfield&gt;.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups. Maximum value: 64



##Example

To configure the default certificate parameters: set aaa certparams -userNameField "Subject:CN" -groupNameField "Subject:OU"

##Related Commands

<ul><li><a href="../../../et-aaa-para/et-aaa-para">set aaa parameter</a></li></ul>



##unset aaa certParams

Use this command to remove aaa certParams settings.Refer to the set aaa certParams command for meanings of the arguments.


##Synopsys

unset aaa certParams [-userNameField] [-groupNameField] [-defaultAuthenticationGroup]


##show aaa certParams

Displays the current client certificate configuration on the NetScaler appliance.


##Synopsys

show aaa certParams


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>twoFactor</b>
The state of the two-factor authentication.

<b>userNameField</b>
The field in the certificate from which the username will be extracted.

<b>groupNameField</b>
The field in the certificate from which the group will be extracted.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.



