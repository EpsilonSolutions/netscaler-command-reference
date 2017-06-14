#authentication samlAction

The following operations can be performed on "authentication samlAction":


[add](#add-authentication-samlaction) | [rm](#rm-authentication-samlaction) | [set](#set-authentication-samlaction) | [unset](#unset-authentication-samlaction) | [show](#show-authentication-samlaction)

##add authentication samlAction

Creates an action (profile) for a Security Assertion Markup Language (SAML) server. The profile contains all configuration data necessary to communicate with that SAML server.


##Synopsys

add authentication samlAction &lt;name> {-samlIdPCertName &lt;string>} {-samlSigningCertName &lt;string>} {-samlRedirectUrl &lt;string>} {-samlACSIndex &lt;positive_integer>} {-samlUserField &lt;string>} {-samlRejectUnsignedAssertion &lt;samlRejectUnsignedAssertion>} {-samlIssuerName &lt;string>} {-samlTwoFactor ( ON | OFF )} [-defaultAuthenticationGroup &lt;string>] [-Attribute1 &lt;string>] [-Attribute2 &lt;string>] [-Attribute3 &lt;string>] [-Attribute4 &lt;string>] [-Attribute5 &lt;string>] [-Attribute6 &lt;string>] [-Attribute7 &lt;string>] [-Attribute8 &lt;string>] [-Attribute9 &lt;string>] [-Attribute10 &lt;string>] [-Attribute11 &lt;string>] [-Attribute12 &lt;string>] [-Attribute13 &lt;string>] [-Attribute14 &lt;string>] [-Attribute15 &lt;string>] [-Attribute16 &lt;string>] {-signatureAlg ( RSA-SHA1 | RSA-SHA256 )} {-digestMethod ( SHA1 | SHA256 )} [-requestedAuthnContext &lt;requestedAuthnContext>] [-authnCtxClassRef &lt;authnCtxClassRef> ...] [-samlBinding ( REDIRECT | POST )] [-attributeConsumingServiceIndex &lt;positive_integer>]


##Arguments

<b>name</b>
Name for the SAML server profile (action). 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after SAML profile is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my authentication action? or ?my authentication action?).

<b>samlIdPCertName</b>
Name of the SAML server as given in that server?s SSL certificate.

<b>samlSigningCertName</b>
Name of the signing authority as given in the SAML server?s SSL certificate.

<b>samlRedirectUrl</b>
URL to which users are redirected for authentication.

<b>samlACSIndex</b>
Index/ID of the metadata entry corresponding to this configuration.
Default value: 255
Minimum value: 0
Maximum value: 255

<b>samlUserField</b>
SAML user ID, as given in the SAML assertion.

<b>samlRejectUnsignedAssertion</b>
Reject unsigned SAML assertions.
Possible values: ON, OFF, STRICT
Default value: NS_ON

<b>samlIssuerName</b>
The name to be used in requests sent from	Netscaler to IdP to uniquely identify Netscaler.

<b>samlTwoFactor</b>
Option to enable second factor after SAML
Possible values: ON, OFF
Default value: NS_OFF

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.
Maximum value: 64

<b>Attribute1</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute1
Maximum value: 64

<b>Attribute2</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute2
Maximum value: 64

<b>Attribute3</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute3
Maximum value: 64

<b>Attribute4</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute4
Maximum value: 64

<b>Attribute5</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute5
Maximum value: 64

<b>Attribute6</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute6
Maximum value: 64

<b>Attribute7</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute7
Maximum value: 64

<b>Attribute8</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute8
Maximum value: 64

<b>Attribute9</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute9
Maximum value: 64

<b>Attribute10</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute10
Maximum value: 64

<b>Attribute11</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute11
Maximum value: 64

<b>Attribute12</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute12
Maximum value: 64

<b>Attribute13</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute13
Maximum value: 64

<b>Attribute14</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute14
Maximum value: 64

<b>Attribute15</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute15
Maximum value: 64

<b>Attribute16</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute16
Maximum value: 64

<b>signatureAlg</b>
Algorithm to be used to sign/verify SAML transactions
Possible values: RSA-SHA1, RSA-SHA256
Default value: SAML_RSA_SHA1

<b>digestMethod</b>
Algorithm to be used to compute/verify digest for SAML transactions
Possible values: SHA1, SHA256
Default value: SAML_SHA1

<b>requestedAuthnContext</b>
This element specifies the authentication context requirements of authentication statements returned in the response.
Possible values: exact, minimum, maximum, better
Default value: SAML_AUTHCTX_EXACT

<b>authnCtxClassRef</b>
This element specifies the authentication class types that are requested from IdP (IdentityProvider).
InternetProtocol: This is applicable when a principal is authenticated through the use of a provided IP address.
InternetProtocolPassword: This is applicable when a principal is authenticated through the use of a provided IP address, in addition to a username/password.
Kerberos: This is applicable when the principal has authenticated using a password to a local authentication authority, in order to acquire a Kerberos ticket.
MobileOneFactorUnregistered: This indicates authentication of the mobile device without requiring explicit end-user interaction.
MobileTwoFactorUnregistered: This indicates two-factor based authentication during mobile customer registration process, such as secure device and user PIN.
MobileOneFactorContract: Reflects mobile contract customer registration procedures and a single factor authentication.
MobileTwoFactorContract: Reflects mobile contract customer registration procedures and a two-factor based authentication.
Password: This class is applicable when a principal authenticates using password over unprotected http session.
PasswordProtectedTransport: This class is applicable when a principal authenticates to an authentication authority through the presentation of a password over a protected session.
PreviousSession: This class is applicable when a principal had authenticated to an authentication authority at some point in the past using any authentication context.
X509: This indicates that the principal authenticated by means of a digital signature where the key was validated as part of an X.509 Public Key Infrastructure.
PGP: This indicates that the principal authenticated by means of a digital signature where the key was validated as part of a PGP Public Key Infrastructure.
SPKI: This indicates that the principal authenticated by means of a digital signature where the key was validated via an SPKI Infrastructure.
XMLDSig: This indicates that the principal authenticated by means of a digital signature according to the processing rules specified in the XML Digital Signature specification.
Smartcard: This indicates that the principal has authenticated using smartcard.
SmartcardPKI: This class is applicable when a principal authenticates to an authentication authority through a two-factor authentication mechanism using a smartcard with enclosed private key and a PIN.
SoftwarePKI: This class is applicable when a principal uses an X.509 certificate stored in software to authenticate to the authentication authority.
Telephony: This class is used to indicate that the principal authenticated via the provision of a fixed-line telephone number, transported via a telephony protocol such as ADSL.
NomadTelephony: Indicates that the principal is "roaming" and authenticates via the means of the line number, a user suffix, and a password element.
PersonalTelephony: This class is used to indicate that the principal authenticated via the provision of a fixed-line telephone.
AuthenticatedTelephony: Indicates that the principal authenticated via the means of the line number, a user suffix, and a password element.
SecureRemotePassword: This class is applicable when the authentication was performed by means of Secure Remote Password.
TLSClient: This class indicates that the principal authenticated by means of a client certificate, secured with the SSL/TLS transport.
TimeSyncToken: This is applicable when a principal authenticates through a time synchronization token.
Unspecified: This indicates that the authentication was performed by unspecified means.
Windows: This indicates that Windows integrated authentication is utilized for authentication.

<b>samlBinding</b>
This element specifies the transport mechanism of saml messages.
Possible values: REDIRECT, POST
Default value: SAML_POST

<b>attributeConsumingServiceIndex</b>
Index/ID of the attribute specification at Identity Provider (IdP). IdP will locate attributes requested by SP using this index and send those attributes in Assertion
Default value: 255
Minimum value: 0
Maximum value: 255



##rm authentication samlAction

Removes a SAML profile (action). An action cannot be removed if it is bound to a policy.


##Synopsys

rm authentication samlAction &lt;name>


##Arguments

<b>name</b>
Name of the SAML profile to be removed.



##set authentication samlAction

Modifies the specified parameters of a SAML server profile (action).


##Synopsys

set authentication samlAction &lt;name> [-samlIdPCertName &lt;string>] [-samlSigningCertName &lt;string>] [-samlRedirectUrl &lt;string>] [-samlACSIndex &lt;positive_integer>] [-samlUserField &lt;string>] [-samlRejectUnsignedAssertion &lt;samlRejectUnsignedAssertion>] [-samlIssuerName &lt;string>] [-samlTwoFactor ( ON | OFF )] [-defaultAuthenticationGroup &lt;string>] [-Attribute1 &lt;string>] [-Attribute2 &lt;string>] [-Attribute3 &lt;string>] [-Attribute4 &lt;string>] [-Attribute5 &lt;string>] [-Attribute6 &lt;string>] [-Attribute7 &lt;string>] [-Attribute8 &lt;string>] [-Attribute9 &lt;string>] [-Attribute10 &lt;string>] [-Attribute11 &lt;string>] [-Attribute12 &lt;string>] [-Attribute13 &lt;string>] [-Attribute14 &lt;string>] [-Attribute15 &lt;string>] [-Attribute16 &lt;string>] [-signatureAlg ( RSA-SHA1 | RSA-SHA256 )] [-digestMethod ( SHA1 | SHA256 )] [-requestedAuthnContext &lt;requestedAuthnContext>] [-authnCtxClassRef &lt;authnCtxClassRef> ...] [-samlBinding ( REDIRECT | POST )] [-attributeConsumingServiceIndex &lt;positive_integer>]


##Arguments

<b>name</b>
Name of the SAML profile (action) to modify.

<b>samlIdPCertName</b>
Name of the SAML server as given in that server?s SSL certificate.

<b>samlSigningCertName</b>
Name of the signing authority as given in the SAML server?s SSL certificate.

<b>samlRedirectUrl</b>
URL to which users are redirected for authentication.

<b>samlACSIndex</b>
Index/ID of the metadata entry corresponding to this configuration.
Default value: 255
Minimum value: 0
Maximum value: 255

<b>samlUserField</b>
SAML user ID, as given in the SAML assertion.

<b>samlRejectUnsignedAssertion</b>
Reject unsigned SAML assertions.
Possible values: ON, OFF, STRICT
Default value: NS_ON

<b>samlIssuerName</b>
The name to be used in requests sent from	Netscaler to IdP to uniquely identify Netscaler.

<b>samlTwoFactor</b>
Option to enable second factor after SAML
Possible values: ON, OFF
Default value: NS_OFF

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.
Maximum value: 64

<b>Attribute1</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute1
Maximum value: 64

<b>Attribute2</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute2
Maximum value: 64

<b>Attribute3</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute3
Maximum value: 64

<b>Attribute4</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute4
Maximum value: 64

<b>Attribute5</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute5
Maximum value: 64

<b>Attribute6</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute6
Maximum value: 64

<b>Attribute7</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute7
Maximum value: 64

<b>Attribute8</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute8
Maximum value: 64

<b>Attribute9</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute9
Maximum value: 64

<b>Attribute10</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute10
Maximum value: 64

<b>Attribute11</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute11
Maximum value: 64

<b>Attribute12</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute12
Maximum value: 64

<b>Attribute13</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute13
Maximum value: 64

<b>Attribute14</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute14
Maximum value: 64

<b>Attribute15</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute15
Maximum value: 64

<b>Attribute16</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute16
Maximum value: 64

<b>signatureAlg</b>
Algorithm to be used to sign/verify SAML transactions
Possible values: RSA-SHA1, RSA-SHA256
Default value: SAML_RSA_SHA1

<b>digestMethod</b>
Algorithm to be used to compute/verify digest for SAML transactions
Possible values: SHA1, SHA256
Default value: SAML_SHA1

<b>requestedAuthnContext</b>
This element specifies the authentication context requirements of authentication statements returned in the response.
Possible values: exact, minimum, maximum, better
Default value: SAML_AUTHCTX_EXACT

<b>authnCtxClassRef</b>
This element specifies the authentication class types that are requested from IdP (IdentityProvider).
InternetProtocol: This is applicable when a principal is authenticated through the use of a provided IP address.
InternetProtocolPassword: This is applicable when a principal is authenticated through the use of a provided IP address, in addition to a username/password.
Kerberos: This is applicable when the principal has authenticated using a password to a local authentication authority, in order to acquire a Kerberos ticket.
MobileOneFactorUnregistered: This indicates authentication of the mobile device without requiring explicit end-user interaction.
MobileTwoFactorUnregistered: This indicates two-factor based authentication during mobile customer registration process, such as secure device and user PIN.
MobileOneFactorContract: Reflects mobile contract customer registration procedures and a single factor authentication.
MobileTwoFactorContract: Reflects mobile contract customer registration procedures and a two-factor based authentication.
Password: This class is applicable when a principal authenticates using password over unprotected http session.
PasswordProtectedTransport: This class is applicable when a principal authenticates to an authentication authority through the presentation of a password over a protected session.
PreviousSession: This class is applicable when a principal had authenticated to an authentication authority at some point in the past using any authentication context.
X509: This indicates that the principal authenticated by means of a digital signature where the key was validated as part of an X.509 Public Key Infrastructure.
PGP: This indicates that the principal authenticated by means of a digital signature where the key was validated as part of a PGP Public Key Infrastructure.
SPKI: This indicates that the principal authenticated by means of a digital signature where the key was validated via an SPKI Infrastructure.
XMLDSig: This indicates that the principal authenticated by means of a digital signature according to the processing rules specified in the XML Digital Signature specification.
Smartcard: This indicates that the principal has authenticated using smartcard.
SmartcardPKI: This class is applicable when a principal authenticates to an authentication authority through a two-factor authentication mechanism using a smartcard with enclosed private key and a PIN.
SoftwarePKI: This class is applicable when a principal uses an X.509 certificate stored in software to authenticate to the authentication authority.
Telephony: This class is used to indicate that the principal authenticated via the provision of a fixed-line telephone number, transported via a telephony protocol such as ADSL.
NomadTelephony: Indicates that the principal is "roaming" and authenticates via the means of the line number, a user suffix, and a password element.
PersonalTelephony: This class is used to indicate that the principal authenticated via the provision of a fixed-line telephone.
AuthenticatedTelephony: Indicates that the principal authenticated via the means of the line number, a user suffix, and a password element.
SecureRemotePassword: This class is applicable when the authentication was performed by means of Secure Remote Password.
TLSClient: This class indicates that the principal authenticated by means of a client certificate, secured with the SSL/TLS transport.
TimeSyncToken: This is applicable when a principal authenticates through a time synchronization token.
Unspecified: This indicates that the authentication was performed by unspecified means.
Windows: This indicates that Windows integrated authentication is utilized for authentication.

<b>samlBinding</b>
This element specifies the transport mechanism of saml messages.
Possible values: REDIRECT, POST
Default value: SAML_POST

<b>attributeConsumingServiceIndex</b>
Index/ID of the attribute specification at Identity Provider (IdP). IdP will locate attributes requested by SP using this index and send those attributes in Assertion
Default value: 255
Minimum value: 0
Maximum value: 255



##unset authentication samlAction

Use this command to remove authentication samlAction settings.Refer to the set authentication samlAction command for meanings of the arguments.


##Synopsys

unset authentication samlAction &lt;name> [-samlIdPCertName] [-samlSigningCertName] [-samlRedirectUrl] [-samlACSIndex] [-samlUserField] [-samlRejectUnsignedAssertion] [-samlIssuerName] [-samlTwoFactor] [-defaultAuthenticationGroup] [-Attribute1] [-Attribute2] [-Attribute3] [-Attribute4] [-Attribute5] [-Attribute6] [-Attribute7] [-Attribute8] [-Attribute9] [-Attribute10] [-Attribute11] [-Attribute12] [-Attribute13] [-Attribute14] [-Attribute15] [-Attribute16] [-signatureAlg] [-digestMethod] [-requestedAuthnContext] [-authnCtxClassRef] [-samlBinding] [-attributeConsumingServiceIndex]


##show authentication samlAction

Displays the current configuration settings for the specified SAML server profile (action).


##Synopsys

show authentication samlAction [&lt;name>]


##Arguments

<b>name</b>
Name of the SAML server profile.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>samlIdPCertName</b>
Name of the SAML server as given in that server?s SSL certificate.

<b>samlSigningCertName</b>
Name of the signing authority as given in the SAML server?s SSL certificate.

<b>samlRedirectUrl</b>
URL to which users are redirected for authentication.

<b>samlACSIndex</b>
Index/ID of the metadata entry corresponding to this configuration.

<b>samlUserField</b>
SAML user ID, as given in the SAML assertion.

<b>samlRejectUnsignedAssertion</b>
Reject unsigned SAML assertions.

<b>samlIssuerName</b>
The name to be used in requests sent from	Netscaler to IdP to uniquely identify Netscaler.

<b>samlTwoFactor</b>
Option to enable second factor after SAML

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.

<b>Attribute1</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute1

<b>Attribute2</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute2

<b>Attribute3</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute3

<b>Attribute4</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute4

<b>Attribute5</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute5

<b>Attribute6</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute6

<b>Attribute7</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute7

<b>Attribute8</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute8

<b>Attribute9</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute9

<b>Attribute10</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute10

<b>Attribute11</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute11

<b>Attribute12</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute12

<b>Attribute13</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute13

<b>Attribute14</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute14

<b>Attribute15</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute15

<b>Attribute16</b>
Name of the attribute in SAML Assertion whose value needs to be extracted and stored as attribute16

<b>signatureAlg</b>
Algorithm to be used to sign/verify SAML transactions

<b>digestMethod</b>
Algorithm to be used to compute/verify digest for SAML transactions

<b>requestedAuthnContext</b>
This element specifies the authentication context requirements of authentication statements returned in the response.

<b>authnCtxClassRef</b>
This element specifies the authentication class types that are requested from IdP (IdentityProvider).
InternetProtocol: This is applicable when a principal is authenticated through the use of a provided IP address.
InternetProtocolPassword: This is applicable when a principal is authenticated through the use of a provided IP address, in addition to a username/password.
Kerberos: This is applicable when the principal has authenticated using a password to a local authentication authority, in order to acquire a Kerberos ticket.
MobileOneFactorUnregistered: This indicates authentication of the mobile device without requiring explicit end-user interaction.
MobileTwoFactorUnregistered: This indicates two-factor based authentication during mobile customer registration process, such as secure device and user PIN.
MobileOneFactorContract: Reflects mobile contract customer registration procedures and a single factor authentication.
MobileTwoFactorContract: Reflects mobile contract customer registration procedures and a two-factor based authentication.
Password: This class is applicable when a principal authenticates using password over unprotected http session.
PasswordProtectedTransport: This class is applicable when a principal authenticates to an authentication authority through the presentation of a password over a protected session.
PreviousSession: This class is applicable when a principal had authenticated to an authentication authority at some point in the past using any authentication context.
X509: This indicates that the principal authenticated by means of a digital signature where the key was validated as part of an X.509 Public Key Infrastructure.
PGP: This indicates that the principal authenticated by means of a digital signature where the key was validated as part of a PGP Public Key Infrastructure.
SPKI: This indicates that the principal authenticated by means of a digital signature where the key was validated via an SPKI Infrastructure.
XMLDSig: This indicates that the principal authenticated by means of a digital signature according to the processing rules specified in the XML Digital Signature specification.
Smartcard: This indicates that the principal has authenticated using smartcard.
SmartcardPKI: This class is applicable when a principal authenticates to an authentication authority through a two-factor authentication mechanism using a smartcard with enclosed private key and a PIN.
SoftwarePKI: This class is applicable when a principal uses an X.509 certificate stored in software to authenticate to the authentication authority.
Telephony: This class is used to indicate that the principal authenticated via the provision of a fixed-line telephone number, transported via a telephony protocol such as ADSL.
NomadTelephony: Indicates that the principal is "roaming" and authenticates via the means of the line number, a user suffix, and a password element.
PersonalTelephony: This class is used to indicate that the principal authenticated via the provision of a fixed-line telephone.
AuthenticatedTelephony: Indicates that the principal authenticated via the means of the line number, a user suffix, and a password element.
SecureRemotePassword: This class is applicable when the authentication was performed by means of Secure Remote Password.
TLSClient: This class indicates that the principal authenticated by means of a client certificate, secured with the SSL/TLS transport.
TimeSyncToken: This is applicable when a principal authenticates through a time synchronization token.
Unspecified: This indicates that the authentication was performed by unspecified means.
Windows: This indicates that Windows integrated authentication is utilized for authentication.

<b>samlBinding</b>
This element specifies the transport mechanism of saml messages.

<b>attributeConsumingServiceIndex</b>
Index/ID of the attribute specification at Identity Provider (IdP). IdP will locate attributes requested by SP using this index and send those attributes in Assertion

<b>devno</b>

<b>count</b>

<b>stateflag</b>



