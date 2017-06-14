#authentication negotiateAction

The following operations can be performed on "authentication negotiateAction":


[add](#add-authentication-negotiateaction) | [rm](#rm-authentication-negotiateaction) | [set](#set-authentication-negotiateaction) | [unset](#unset-authentication-negotiateaction) | [show](#show-authentication-negotiateaction)

##add authentication negotiateAction

Creates an action (profile) for an Active Directory (AD) server that is used as a Kerberos Key Distribution Center (KDC). The profile contains all configuration data necessary to communicate with that AD KDC server.


##Synopsys

add authentication negotiateAction &lt;name> {-domain &lt;string>} {-domainUser &lt;string>} {-domainUserPasswd } {-OU &lt;string>} [-defaultAuthenticationGroup &lt;string>] [-keytab &lt;string>]


##Arguments

<b>name</b>
Name for the AD KDC server profile (negotiate action). 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after AD KDC server profile is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my authentication action? or ?my authentication action?).

<b>domain</b>
Domain name of the AD KDC server.

<b>domainUser</b>
User name that the NetScaler appliance uses to join the AD KDC server domain. 
The NetScaler appliance uses the domain user name to check the health of the AD KDC server.

<b>domainUserPasswd</b>
Password that the NetScaler appliance uses to join the AD KDC server domain.

<b>OU</b>
Active Directory organizational units (OU) attribute.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.
Maximum value: 64

<b>keytab</b>
The path to the keytab file



##rm authentication negotiateAction

Removes an AD KDC server profile (negotiate action). An action cannot be removed if it is bound to a policy.


##Synopsys

rm authentication negotiateAction &lt;name>


##Arguments

<b>name</b>
Name of the AD KDC server profile to be removed.



##set authentication negotiateAction

Configures an AD KDC server profile (negotiate action).


##Synopsys

set authentication negotiateAction &lt;name> [-domain &lt;string>] [-domainUser &lt;string>] [-domainUserPasswd ] [-OU &lt;string>] [-defaultAuthenticationGroup &lt;string>] [-keytab &lt;string>]


##Arguments

<b>name</b>
Name of the AD KDC server profile.

<b>domain</b>
Domain name of the AD KDC server.

<b>domainUser</b>
User name that the NetScaler appliance uses to join the AD KDC server domain. 
The NetScaler appliance uses the domain user name to check the health of the AD KDC server.

<b>domainUserPasswd</b>
Password that the NetScaler appliance uses to join the AD KDC server domain.

<b>OU</b>
Active Directory organizational units (OU) attribute.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.
Maximum value: 64

<b>keytab</b>
The path to the keytab file



##unset authentication negotiateAction

Use this command to remove authentication negotiateAction settings.Refer to the set authentication negotiateAction command for meanings of the arguments.


##Synopsys

unset authentication negotiateAction &lt;name> [-domain] [-domainUser] [-domainUserPasswd] [-OU] [-defaultAuthenticationGroup]


##show authentication negotiateAction

Displays the current configuration settings for the specified AD KDC server profile (negotiate action).


##Synopsys

show authentication negotiateAction [&lt;name>]


##Arguments

<b>name</b>
Name of the AD KDC server profile.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>domain</b>
Domain name of the AD KDC server.

<b>domainUser</b>
User name that the NetScaler appliance uses to join the AD KDC server domain. 
The NetScaler appliance uses the domain user name to check the health of the AD KDC server.

<b>domainUserPasswd</b>
Password that the NetScaler appliance uses to join the AD KDC server domain.

<b>OU</b>
Active Directory organizational units (OU) attribute.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.

<b>keytab</b>
The path to the keytab file

<b>kcdSPN</b>
Host SPN extracted from keytab file.

<b>stateflag</b>

<b>devno</b>

<b>count</b>



