#authentication samlIdPProfile

The following operations can be performed on "authentication samlIdPProfile":


[add](#add-authentication-samlidpprofile) | [rm](#rm-authentication-samlidpprofile) | [set](#set-authentication-samlidpprofile) | [unset](#unset-authentication-samlidpprofile) | [show](#show-authentication-samlidpprofile)

##add authentication samlIdPProfile

Creates a SAML single IdP profile. This profile is used in verifying incoming authentication request from Service Provider and creating and signing Assertion that is sent to the same.


##Synopsys

add authentication samlIdPProfile &lt;name> [-samlSPCertName &lt;string>] [-samlIdPCertName &lt;string>] [-assertionConsumerServiceURL &lt;URL>] [-sendPassword ( ON | OFF )] [-samlIssuerName &lt;string>] [-audience &lt;string>]


##Arguments

<b>name</b>
Name for the new saml single sign-on profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after an SSO action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').

<b>samlSPCertName</b>
Name of the SSL certificate of SAML Relying Party. This certificate is used to verify signature of the incoming AuthnRequest from a Relying Party or Service Provider

<b>samlIdPCertName</b>
Name of the signing authority as given in the SAML server?s SSL certificate. This certificate is used to sign the SAMLResposne that is sent to Relying Party or Service Provider after successful authentication

<b>assertionConsumerServiceURL</b>
URL to which the assertion is to be sent.

<b>sendPassword</b>
Option to send password in assertion.
Possible values: ON, OFF
Default value: OFF

<b>samlIssuerName</b>
The name to be used in requests sent from	Netscaler to IdP to uniquely identify Netscaler.

<b>audience</b>
Audience for which assertion sent by IdP is applicable. This is typically entity name or url that represents ServiceProvider
Maximum value: 256



##rm authentication samlIdPProfile

Deletes an existing saml IdP profile.


##Synopsys

rm authentication samlIdPProfile &lt;name>


##Arguments

<b>name</b>
Name for the new saml single sign-on profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after an SSO action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').



##set authentication samlIdPProfile

Modifies the specified attributes of a saml IdP profile.


##Synopsys

set authentication samlIdPProfile &lt;name> [-samlSPCertName &lt;string>] [-samlIdPCertName &lt;string>] [-assertionConsumerServiceURL &lt;URL>] [-sendPassword ( ON | OFF )] [-samlIssuerName &lt;string>] [-audience &lt;string>]


##Arguments

<b>name</b>
Name for the new saml single sign-on profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after an SSO action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').

<b>samlSPCertName</b>
Name of the SSL certificate of SAML Relying Party. This certificate is used to verify signature of the incoming AuthnRequest from a Relying Party or Service Provider

<b>samlIdPCertName</b>
Name of the signing authority as given in the SAML server?s SSL certificate. This certificate is used to sign the SAMLResposne that is sent to Relying Party or Service Provider after successful authentication

<b>assertionConsumerServiceURL</b>
URL to which the assertion is to be sent.

<b>sendPassword</b>
Option to send password in assertion.
Possible values: ON, OFF
Default value: OFF

<b>samlIssuerName</b>
The name to be used in requests sent from	Netscaler to IdP to uniquely identify Netscaler.

<b>audience</b>
Audience for which assertion sent by IdP is applicable. This is typically entity name or url that represents ServiceProvider
Maximum value: 256



##unset authentication samlIdPProfile

Use this command to remove authentication samlIdPProfile settings.Refer to the set authentication samlIdPProfile command for meanings of the arguments.


##Synopsys

unset authentication samlIdPProfile &lt;name> [-samlSPCertName] [-samlIdPCertName] [-assertionConsumerServiceURL] [-sendPassword] [-samlIssuerName] [-audience]


##show authentication samlIdPProfile

Displays information about all configured saml single sign-on profiles, or displays detailed information about the specified action.


##Synopsys

show authentication samlIdPProfile [&lt;name>]


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

<b>samlSPCertName</b>
Name of the SSL certificate of SAML Relying Party. This certificate is used to verify signature of the incoming AuthnRequest from a Relying Party or Service Provider

<b>samlIdPCertName</b>
Name of the signing authority as given in the SAML server?s SSL certificate. This certificate is used to sign the SAMLResposne that is sent to Relying Party or Service Provider after successful authentication

<b>assertionConsumerServiceURL</b>
URL to which the assertion is to be sent.

<b>sendPassword</b>
Option to send password in assertion.

<b>samlIssuerName</b>
The name to be used in requests sent from	Netscaler to IdP to uniquely identify Netscaler.

<b>audience</b>
Audience for which assertion sent by IdP is applicable. This is typically entity name or url that represents ServiceProvider

<b>devno</b>

<b>count</b>

<b>stateflag</b>



