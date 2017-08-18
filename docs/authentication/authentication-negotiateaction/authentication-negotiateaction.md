#authentication negotiateAction

The following operations can be performed on "authentication negotiateAction":


[add](#add-authentication-negotiateaction) | [rm](#rm-authentication-negotiateaction) | [set](#set-authentication-negotiateaction) | [unset](#unset-authentication-negotiateaction) | [show](#show-authentication-negotiateaction)

##add authentication negotiateAction

Creates an action (profile) for an Active Directory (AD) server that is used as a Kerberos Key Distribution Center (KDC). The profile contains all configuration data necessary to communicate with that AD KDC server.


##Synopsys

add authentication negotiateAction &lt;name> {-domain &lt;string>} {-domainUser &lt;string>} {-domainUserPasswd } [-defaultAuthenticationGroup &lt;string>] [-keytab &lt;string>] [-NTLMPath &lt;string>]


##Arguments

<b>name</b>
Name for the AD KDC server profile (negotiate action). 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after AD KDC server profile is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my authentication action" or 'my authentication action').

<b>domain</b>
Domain name of the service principal that represnts Netscaler.

<b>domainUser</b>
User name of the account that is mapped with Netscaler principal. This can be given along with domain and password when keytab file is not available. If username is given along with keytab file, then that keytab file will be searched for this user's credentials.

<b>domainUserPasswd</b>
Password of the account that is mapped to the NetScaler principal.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.

<b>keytab</b>
The path to the keytab file that is used to decrypt kerberos tickets presented to Netscaler. If keytab is not available, domain/username/password can be specified in the negotiate action configuration

<b>NTLMPath</b>
The path to the site that is enabled for NTLM authentication, including FQDN of the server. This is used when clients fallback to NTLM.



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

set authentication negotiateAction &lt;name> [-domain &lt;string>] [-domainUser &lt;string>] [-domainUserPasswd ] [-defaultAuthenticationGroup &lt;string>] [-keytab &lt;string>] [-NTLMPath &lt;string>]


##Arguments

<b>name</b>
Name of the AD KDC server profile.

<b>domain</b>
Domain name of the service principal that represnts Netscaler.

<b>domainUser</b>
User name of the account that is mapped with Netscaler principal. This can be given along with domain and password when keytab file is not available. If username is given along with keytab file, then that keytab file will be searched for this user's credentials.

<b>domainUserPasswd</b>
Password of the account that is mapped to the NetScaler principal.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.

<b>keytab</b>
The path to the keytab file that is used to decrypt kerberos tickets presented to Netscaler. If keytab is not available, domain/username/password can be specified in the negotiate action configuration

<b>NTLMPath</b>
The path to the site that is enabled for NTLM authentication, including FQDN of the server. This is used when clients fallback to NTLM.



##unset authentication negotiateAction

Use this command to remove authentication negotiateAction settings.Refer to the set authentication negotiateAction command for meanings of the arguments.


##Synopsys

unset authentication negotiateAction &lt;name> [-domain] [-domainUser] [-domainUserPasswd] [-defaultAuthenticationGroup] [-NTLMPath]


##show authentication negotiateAction

Displays the current configuration settings for the specified AD KDC server profile (negotiate action).


##Synopsys

show authentication negotiateAction [&lt;name>]


##Arguments

<b>name</b>
Name of the AD KDC server profile.



##Outputs

<b>domain</b>
Domain name of the service principal that represnts Netscaler.

<b>domainUser</b>
User name of the account that is mapped with Netscaler principal. This can be given along with domain and password when keytab file is not available. If username is given along with keytab file, then that keytab file will be searched for this user's credentials.

<b>domainUserPasswd</b>
Password of the account that is mapped to the NetScaler principal.

<b>OU</b>
Active Directory organizational units (OU) attribute.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.

<b>keytab</b>
The path to the keytab file that is used to decrypt kerberos tickets presented to Netscaler. If keytab is not available, domain/username/password can be specified in the negotiate action configuration

<b>kcdSPN</b>
Host SPN extracted from keytab file.

<b>NTLMPath</b>
The path to the site that is enabled for NTLM authentication, including FQDN of the server. This is used when clients fallback to NTLM.

<b>stateflag</b>

<b>devno</b>

<b>count</b>



