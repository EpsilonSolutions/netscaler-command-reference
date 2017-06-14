#vpn samlSSOProfile

The following operations can be performed on "vpn samlSSOProfile":


[add](#add-vpn-samlssoprofile) | [rm](#rm-vpn-samlssoprofile) | [set](#set-vpn-samlssoprofile) | [unset](#unset-vpn-samlssoprofile) | [show](#show-vpn-samlssoprofile)

##add vpn samlSSOProfile

Creates a SAML single sign-on profile. This profile is employed in triggering saml assertion to a target service based on traffic profile.


##Synopsys

add vpn samlSSOProfile &lt;name> -samlSigningCertName &lt;string> -assertionConsumerServiceURL &lt;URL> -relaystateRule &lt;expression> [-sendPassword ( ON | OFF )] [-samlIssuerName &lt;string>]


##Arguments

<b>name</b>
Name for the new saml single sign-on profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after an SSO action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').

<b>samlSigningCertName</b>
Name of the signing authority as given in the SAML server?s SSL certificate.

<b>assertionConsumerServiceURL</b>
URL to which the assertion is to be sent.

<b>relaystateRule</b>
Expression to extract relaystate to be sent along with assertion. Evaluation of this expression should return TEXT content. This is typically a target url to which user is redirected after the recipient validates SAML token

<b>sendPassword</b>
Option to send password in assertion.
Possible values: ON, OFF
Default value: OFF

<b>samlIssuerName</b>
The name to be used in requests sent from	Netscaler to IdP to uniquely identify Netscaler.



##rm vpn samlSSOProfile

Deletes an existing saml single sign-on traffic profile.


##Synopsys

rm vpn samlSSOProfile &lt;name>


##Arguments

<b>name</b>
Name for the new saml single sign-on profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after an SSO action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').



##set vpn samlSSOProfile

Modifies the specified attributes of a saml single sign-on traffic profile.


##Synopsys

set vpn samlSSOProfile &lt;name> [-samlSigningCertName &lt;string>] [-assertionConsumerServiceURL &lt;URL>] [-sendPassword ( ON | OFF )] [-samlIssuerName &lt;string>] [-relaystateRule &lt;expression>]


##Arguments

<b>name</b>
Name for the new saml single sign-on profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after an SSO action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').

<b>samlSigningCertName</b>
Name of the signing authority as given in the SAML server?s SSL certificate.

<b>assertionConsumerServiceURL</b>
URL to which the assertion is to be sent.

<b>sendPassword</b>
Option to send password in assertion.
Possible values: ON, OFF
Default value: OFF

<b>samlIssuerName</b>
The name to be used in requests sent from	Netscaler to IdP to uniquely identify Netscaler.

<b>relaystateRule</b>
Expression to extract relaystate to be sent along with assertion. Evaluation of this expression should return TEXT content. This is typically a target url to which user is redirected after the recipient validates SAML token



##unset vpn samlSSOProfile

Use this command to remove vpn samlSSOProfile settings.Refer to the set vpn samlSSOProfile command for meanings of the arguments.


##Synopsys

unset vpn samlSSOProfile &lt;name> [-samlSigningCertName] [-sendPassword] [-samlIssuerName]


##show vpn samlSSOProfile

Displays information about all configured saml single sign-on profiles, or displays detailed information about the specified action.


##Synopsys

show vpn samlSSOProfile [&lt;name>]


##Arguments

<b>name</b>
Name for the new saml single sign-on profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after an SSO action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>samlSigningCertName</b>
Name of the signing authority as given in the SAML server?s SSL certificate.

<b>assertionConsumerServiceURL</b>
URL to which the assertion is to be sent.

<b>sendPassword</b>
Option to send password in assertion.

<b>samlIssuerName</b>
The name to be used in requests sent from	Netscaler to IdP to uniquely identify Netscaler.

<b>relaystateRule</b>
Expression to extract relaystate to be sent along with assertion. Evaluation of this expression should return TEXT content. This is typically a target url to which user is redirected after the recipient validates SAML token

<b>devno</b>

<b>count</b>

<b>stateflag</b>



