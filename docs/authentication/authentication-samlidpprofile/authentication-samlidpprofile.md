#authentication samlIdPProfile

The following operations can be performed on "authentication samlIdPProfile":


[add](#add-authentication-samlidpprofile) | [rm](#rm-authentication-samlidpprofile) | [set](#set-authentication-samlidpprofile) | [unset](#unset-authentication-samlidpprofile) | [show](#show-authentication-samlidpprofile)

##add authentication samlIdPProfile

Creates a SAML single IdP profile. This profile is used in verifying incoming authentication request from Service Provider and creating and signing Assertion that is sent to the same.


##Synopsys

add authentication samlIdPProfile &lt;name> [-samlSPCertName &lt;string>  [-encryptAssertion ( ON | OFF )]] [-samlIdPCertName &lt;string>] [-assertionConsumerServiceURL &lt;URL>] [-sendPassword ( ON | OFF )] [-samlIssuerName &lt;string>] [-rejectUnsignedRequests ( ON | OFF )] [-signatureAlg ( RSA-SHA1 | RSA-SHA256 )] [-digestMethod ( SHA1 | SHA256 )] [-audience &lt;string>] [-NameIDFormat &lt;NameIDFormat>] [-NameIDExpr &lt;string>] [-Attribute1 &lt;string>  -Attribute1Expr &lt;string>  [-Attribute1FriendlyName &lt;string>]  [-Attribute1Format ( URI | Basic )]] [-Attribute2 &lt;string>  -Attribute2Expr &lt;string>  [-Attribute2FriendlyName &lt;string>]  [-Attribute2Format ( URI | Basic )]] [-Attribute3 &lt;string>  -Attribute3Expr &lt;string>  [-Attribute3FriendlyName &lt;string>]  [-Attribute3Format ( URI | Basic )]] [-Attribute4 &lt;string>  -Attribute4Expr &lt;string>  [-Attribute4FriendlyName &lt;string>]  [-Attribute4Format ( URI | Basic )]] [-Attribute5 &lt;string>  -Attribute5Expr &lt;string>  [-Attribute5FriendlyName &lt;string>]  [-Attribute5Format ( URI | Basic )]] [-Attribute6 &lt;string>  -Attribute6Expr &lt;string>  [-Attribute6FriendlyName &lt;string>]  [-Attribute6Format ( URI | Basic )]] [-Attribute7 &lt;string>  -Attribute7Expr &lt;string>  [-Attribute7FriendlyName &lt;string>]  [-Attribute7Format ( URI | Basic )]] [-Attribute8 &lt;string>  -Attribute8Expr &lt;string>  [-Attribute8FriendlyName &lt;string>]  [-Attribute8Format ( URI | Basic )]] [-Attribute9 &lt;string>  -Attribute9Expr &lt;string>  [-Attribute9FriendlyName &lt;string>]  [-Attribute9Format ( URI | Basic )]] [-Attribute10 &lt;string>  -Attribute10Expr &lt;string>  [-Attribute10FriendlyName &lt;string>]  [-Attribute10Format ( URI | Basic )]] [-Attribute11 &lt;string>  -Attribute11Expr &lt;string>  [-Attribute11FriendlyName &lt;string>]  [-Attribute11Format ( URI | Basic )]] [-Attribute12 &lt;string>  -Attribute12Expr &lt;string>  [-Attribute12FriendlyName &lt;string>]  [-Attribute12Format ( URI | Basic )]] [-Attribute13 &lt;string>  -Attribute13Expr &lt;string>  [-Attribute13FriendlyName &lt;string>]  [-Attribute13Format ( URI | Basic )]] [-Attribute14 &lt;string>  -Attribute14Expr &lt;string>  [-Attribute14FriendlyName &lt;string>]  [-Attribute14Format ( URI | Basic )]] [-Attribute15 &lt;string>  -Attribute15Expr &lt;string>  [-Attribute15FriendlyName &lt;string>]  [-Attribute15Format ( URI | Basic )]] [-Attribute16 &lt;string>  -Attribute16Expr &lt;string>  [-Attribute16FriendlyName &lt;string>]  [-Attribute16Format ( URI | Basic )]] [-encryptionAlgorithm &lt;encryptionAlgorithm>]


##Arguments

<b>name</b>
Name for the new saml single sign-on profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after an action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').

<b>samlSPCertName</b>
Name of the SSL certificate of SAML Relying Party. This certificate is used to verify signature of the incoming AuthnRequest from a Relying Party or Service Provider

<b>samlIdPCertName</b>
Name of the signing authority as given in the SAML server's SSL certificate. This certificate is used to sign the SAMLResposne that is sent to Relying Party or Service Provider after successful authentication

<b>assertionConsumerServiceURL</b>
URL to which the assertion is to be sent.

<b>sendPassword</b>
Option to send password in assertion.
Possible values: ON, OFF
Default value: OFF

<b>samlIssuerName</b>
The name to be used in requests sent from	Netscaler to IdP to uniquely identify Netscaler.

<b>rejectUnsignedRequests</b>
Option to Reject unsigned SAML Requests.
Possible values: ON, OFF
Default value: ON

<b>signatureAlg</b>
Algorithm to be used to sign/verify SAML transactions
Possible values: RSA-SHA1, RSA-SHA256
Default value: RSA-SHA1

<b>digestMethod</b>
Algorithm to be used to compute/verify digest for SAML transactions
Possible values: SHA1, SHA256
Default value: SHA1

<b>audience</b>
Audience for which assertion sent by IdP is applicable. This is typically entity name or url that represents ServiceProvider

<b>NameIDFormat</b>
Format of Name Identifier sent in Assertion.
Possible values: Unspecified, emailAddress, X509SubjectName, WindowsDomainQualifiedName, kerberos, entity, persistent, transient
Default value: transient

<b>NameIDExpr</b>
Expression that will be evaluated to obtain NameIdentifier to be sent in assertion

<b>Attribute1</b>
Name of attribute1 that needs to be sent in SAML Assertion

<b>Attribute1Expr</b>
Expression that will be evaluated to obtain attribute1's value to be sent in Assertion

<b>Attribute1FriendlyName</b>
User-Friendly Name of attribute1 that needs to be sent in SAML Assertion

<b>Attribute1Format</b>
Format of Attribute1 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute2</b>
Name of attribute2 that needs to be sent in SAML Assertion

<b>Attribute2Expr</b>
Expression that will be evaluated to obtain attribute2's value to be sent in Assertion

<b>Attribute2FriendlyName</b>
User-Friendly Name of attribute2 that needs to be sent in SAML Assertion

<b>Attribute2Format</b>
Format of Attribute2 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute3</b>
Name of attribute3 that needs to be sent in SAML Assertion

<b>Attribute3Expr</b>
Expression that will be evaluated to obtain attribute3's value to be sent in Assertion

<b>Attribute3FriendlyName</b>
User-Friendly Name of attribute3 that needs to be sent in SAML Assertion

<b>Attribute3Format</b>
Format of Attribute3 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute4</b>
Name of attribute4 that needs to be sent in SAML Assertion

<b>Attribute4Expr</b>
Expression that will be evaluated to obtain attribute4's value to be sent in Assertion

<b>Attribute4FriendlyName</b>
User-Friendly Name of attribute4 that needs to be sent in SAML Assertion

<b>Attribute4Format</b>
Format of Attribute4 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute5</b>
Name of attribute5 that needs to be sent in SAML Assertion

<b>Attribute5Expr</b>
Expression that will be evaluated to obtain attribute5's value to be sent in Assertion

<b>Attribute5FriendlyName</b>
User-Friendly Name of attribute5 that needs to be sent in SAML Assertion

<b>Attribute5Format</b>
Format of Attribute5 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute6</b>
Name of attribute6 that needs to be sent in SAML Assertion

<b>Attribute6Expr</b>
Expression that will be evaluated to obtain attribute6's value to be sent in Assertion

<b>Attribute6FriendlyName</b>
User-Friendly Name of attribute6 that needs to be sent in SAML Assertion

<b>Attribute6Format</b>
Format of Attribute6 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute7</b>
Name of attribute7 that needs to be sent in SAML Assertion

<b>Attribute7Expr</b>
Expression that will be evaluated to obtain attribute7's value to be sent in Assertion

<b>Attribute7FriendlyName</b>
User-Friendly Name of attribute7 that needs to be sent in SAML Assertion

<b>Attribute7Format</b>
Format of Attribute7 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute8</b>
Name of attribute8 that needs to be sent in SAML Assertion

<b>Attribute8Expr</b>
Expression that will be evaluated to obtain attribute8's value to be sent in Assertion

<b>Attribute8FriendlyName</b>
User-Friendly Name of attribute8 that needs to be sent in SAML Assertion

<b>Attribute8Format</b>
Format of Attribute8 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute9</b>
Name of attribute9 that needs to be sent in SAML Assertion

<b>Attribute9Expr</b>
Expression that will be evaluated to obtain attribute9's value to be sent in Assertion

<b>Attribute9FriendlyName</b>
User-Friendly Name of attribute9 that needs to be sent in SAML Assertion

<b>Attribute9Format</b>
Format of Attribute9 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute10</b>
Name of attribute10 that needs to be sent in SAML Assertion

<b>Attribute10Expr</b>
Expression that will be evaluated to obtain attribute10's value to be sent in Assertion

<b>Attribute10FriendlyName</b>
User-Friendly Name of attribute10 that needs to be sent in SAML Assertion

<b>Attribute10Format</b>
Format of Attribute10 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute11</b>
Name of attribute11 that needs to be sent in SAML Assertion

<b>Attribute11Expr</b>
Expression that will be evaluated to obtain attribute11's value to be sent in Assertion

<b>Attribute11FriendlyName</b>
User-Friendly Name of attribute11 that needs to be sent in SAML Assertion

<b>Attribute11Format</b>
Format of Attribute11 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute12</b>
Name of attribute12 that needs to be sent in SAML Assertion

<b>Attribute12Expr</b>
Expression that will be evaluated to obtain attribute12's value to be sent in Assertion

<b>Attribute12FriendlyName</b>
User-Friendly Name of attribute12 that needs to be sent in SAML Assertion

<b>Attribute12Format</b>
Format of Attribute12 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute13</b>
Name of attribute13 that needs to be sent in SAML Assertion

<b>Attribute13Expr</b>
Expression that will be evaluated to obtain attribute13's value to be sent in Assertion

<b>Attribute13FriendlyName</b>
User-Friendly Name of attribute13 that needs to be sent in SAML Assertion

<b>Attribute13Format</b>
Format of Attribute13 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute14</b>
Name of attribute14 that needs to be sent in SAML Assertion

<b>Attribute14Expr</b>
Expression that will be evaluated to obtain attribute14's value to be sent in Assertion

<b>Attribute14FriendlyName</b>
User-Friendly Name of attribute14 that needs to be sent in SAML Assertion

<b>Attribute14Format</b>
Format of Attribute14 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute15</b>
Name of attribute15 that needs to be sent in SAML Assertion

<b>Attribute15Expr</b>
Expression that will be evaluated to obtain attribute15's value to be sent in Assertion

<b>Attribute15FriendlyName</b>
User-Friendly Name of attribute15 that needs to be sent in SAML Assertion

<b>Attribute15Format</b>
Format of Attribute15 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute16</b>
Name of attribute16 that needs to be sent in SAML Assertion

<b>Attribute16Expr</b>
Expression that will be evaluated to obtain attribute16's value to be sent in Assertion

<b>Attribute16FriendlyName</b>
User-Friendly Name of attribute16 that needs to be sent in SAML Assertion

<b>Attribute16Format</b>
Format of Attribute16 to be sent in Assertion.
Possible values: URI, Basic

<b>encryptAssertion</b>
Option to encrypt assertion when Netscaler IDP sends one.
Possible values: ON, OFF
Default value: OFF

<b>encryptionAlgorithm</b>
Algorithm to be used to encrypt SAML assertion
Possible values: DES3, AES128, AES192, AES256
Default value: AES256



##rm authentication samlIdPProfile

Deletes an existing saml IdP profile.


##Synopsys

rm authentication samlIdPProfile &lt;name>


##Arguments

<b>name</b>
Name for the new saml single sign-on profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after an action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').



##set authentication samlIdPProfile

Modifies the specified attributes of a saml IdP profile.


##Synopsys

set authentication samlIdPProfile &lt;name> [-samlSPCertName &lt;string>] [-samlIdPCertName &lt;string>] [-assertionConsumerServiceURL &lt;URL>] [-sendPassword ( ON | OFF )] [-samlIssuerName &lt;string>] [-rejectUnsignedRequests ( ON | OFF )] [-signatureAlg ( RSA-SHA1 | RSA-SHA256 )] [-digestMethod ( SHA1 | SHA256 )] [-audience &lt;string>] [-NameIDFormat &lt;NameIDFormat>] [-NameIDExpr &lt;string>] [-Attribute1 &lt;string>  -Attribute1Expr &lt;string>  [-Attribute1FriendlyName &lt;string>]  [-Attribute1Format ( URI | Basic )]] [-Attribute2 &lt;string>  -Attribute2Expr &lt;string>  [-Attribute2FriendlyName &lt;string>]  [-Attribute2Format ( URI | Basic )]] [-Attribute3 &lt;string>  -Attribute3Expr &lt;string>  [-Attribute3FriendlyName &lt;string>]  [-Attribute3Format ( URI | Basic )]] [-Attribute4 &lt;string>  -Attribute4Expr &lt;string>  [-Attribute4FriendlyName &lt;string>]  [-Attribute4Format ( URI | Basic )]] [-Attribute5 &lt;string>  -Attribute5Expr &lt;string>  [-Attribute5FriendlyName &lt;string>]  [-Attribute5Format ( URI | Basic )]] [-Attribute6 &lt;string>  -Attribute6Expr &lt;string>  [-Attribute6FriendlyName &lt;string>]  [-Attribute6Format ( URI | Basic )]] [-Attribute7 &lt;string>  -Attribute7Expr &lt;string>  [-Attribute7FriendlyName &lt;string>]  [-Attribute7Format ( URI | Basic )]] [-Attribute8 &lt;string>  -Attribute8Expr &lt;string>  [-Attribute8FriendlyName &lt;string>]  [-Attribute8Format ( URI | Basic )]] [-Attribute9 &lt;string>  -Attribute9Expr &lt;string>  [-Attribute9FriendlyName &lt;string>]  [-Attribute9Format ( URI | Basic )]] [-Attribute10 &lt;string>  -Attribute10Expr &lt;string>  [-Attribute10FriendlyName &lt;string>]  [-Attribute10Format ( URI | Basic )]] [-Attribute11 &lt;string>  -Attribute11Expr &lt;string>  [-Attribute11FriendlyName &lt;string>]  [-Attribute11Format ( URI | Basic )]] [-Attribute12 &lt;string>  -Attribute12Expr &lt;string>  [-Attribute12FriendlyName &lt;string>]  [-Attribute12Format ( URI | Basic )]] [-Attribute13 &lt;string>  -Attribute13Expr &lt;string>  [-Attribute13FriendlyName &lt;string>]  [-Attribute13Format ( URI | Basic )]] [-Attribute14 &lt;string>  -Attribute14Expr &lt;string>  [-Attribute14FriendlyName &lt;string>]  [-Attribute14Format ( URI | Basic )]] [-Attribute15 &lt;string>  -Attribute15Expr &lt;string>  [-Attribute15FriendlyName &lt;string>]  [-Attribute15Format ( URI | Basic )]] [-Attribute16 &lt;string>  -Attribute16Expr &lt;string>  [-Attribute16FriendlyName &lt;string>]  [-Attribute16Format ( URI | Basic )]] [-encryptAssertion ( ON | OFF )] [-encryptionAlgorithm &lt;encryptionAlgorithm>]


##Arguments

<b>name</b>
Name for the new saml single sign-on profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after an action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').

<b>samlSPCertName</b>
Name of the SSL certificate of SAML Relying Party. This certificate is used to verify signature of the incoming AuthnRequest from a Relying Party or Service Provider

<b>samlIdPCertName</b>
Name of the signing authority as given in the SAML server's SSL certificate. This certificate is used to sign the SAMLResposne that is sent to Relying Party or Service Provider after successful authentication

<b>assertionConsumerServiceURL</b>
URL to which the assertion is to be sent.

<b>sendPassword</b>
Option to send password in assertion.
Possible values: ON, OFF
Default value: OFF

<b>samlIssuerName</b>
The name to be used in requests sent from	Netscaler to IdP to uniquely identify Netscaler.

<b>rejectUnsignedRequests</b>
Option to Reject unsigned SAML Requests.
Possible values: ON, OFF
Default value: ON

<b>signatureAlg</b>
Algorithm to be used to sign/verify SAML transactions
Possible values: RSA-SHA1, RSA-SHA256
Default value: RSA-SHA1

<b>digestMethod</b>
Algorithm to be used to compute/verify digest for SAML transactions
Possible values: SHA1, SHA256
Default value: SHA1

<b>audience</b>
Audience for which assertion sent by IdP is applicable. This is typically entity name or url that represents ServiceProvider

<b>NameIDFormat</b>
Format of Name Identifier sent in Assertion.
Possible values: Unspecified, emailAddress, X509SubjectName, WindowsDomainQualifiedName, kerberos, entity, persistent, transient
Default value: transient

<b>NameIDExpr</b>
Expression that will be evaluated to obtain NameIdentifier to be sent in assertion

<b>Attribute1</b>
Name of attribute1 that needs to be sent in SAML Assertion

<b>Attribute1Expr</b>
Expression that will be evaluated to obtain attribute1's value to be sent in Assertion

<b>Attribute1FriendlyName</b>
User-Friendly Name of attribute1 that needs to be sent in SAML Assertion

<b>Attribute1Format</b>
Format of Attribute1 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute2</b>
Name of attribute2 that needs to be sent in SAML Assertion

<b>Attribute2Expr</b>
Expression that will be evaluated to obtain attribute2's value to be sent in Assertion

<b>Attribute2FriendlyName</b>
User-Friendly Name of attribute2 that needs to be sent in SAML Assertion

<b>Attribute2Format</b>
Format of Attribute2 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute3</b>
Name of attribute3 that needs to be sent in SAML Assertion

<b>Attribute3Expr</b>
Expression that will be evaluated to obtain attribute3's value to be sent in Assertion

<b>Attribute3FriendlyName</b>
User-Friendly Name of attribute3 that needs to be sent in SAML Assertion

<b>Attribute3Format</b>
Format of Attribute3 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute4</b>
Name of attribute4 that needs to be sent in SAML Assertion

<b>Attribute4Expr</b>
Expression that will be evaluated to obtain attribute4's value to be sent in Assertion

<b>Attribute4FriendlyName</b>
User-Friendly Name of attribute4 that needs to be sent in SAML Assertion

<b>Attribute4Format</b>
Format of Attribute4 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute5</b>
Name of attribute5 that needs to be sent in SAML Assertion

<b>Attribute5Expr</b>
Expression that will be evaluated to obtain attribute5's value to be sent in Assertion

<b>Attribute5FriendlyName</b>
User-Friendly Name of attribute5 that needs to be sent in SAML Assertion

<b>Attribute5Format</b>
Format of Attribute5 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute6</b>
Name of attribute6 that needs to be sent in SAML Assertion

<b>Attribute6Expr</b>
Expression that will be evaluated to obtain attribute6's value to be sent in Assertion

<b>Attribute6FriendlyName</b>
User-Friendly Name of attribute6 that needs to be sent in SAML Assertion

<b>Attribute6Format</b>
Format of Attribute6 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute7</b>
Name of attribute7 that needs to be sent in SAML Assertion

<b>Attribute7Expr</b>
Expression that will be evaluated to obtain attribute7's value to be sent in Assertion

<b>Attribute7FriendlyName</b>
User-Friendly Name of attribute7 that needs to be sent in SAML Assertion

<b>Attribute7Format</b>
Format of Attribute7 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute8</b>
Name of attribute8 that needs to be sent in SAML Assertion

<b>Attribute8Expr</b>
Expression that will be evaluated to obtain attribute8's value to be sent in Assertion

<b>Attribute8FriendlyName</b>
User-Friendly Name of attribute8 that needs to be sent in SAML Assertion

<b>Attribute8Format</b>
Format of Attribute8 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute9</b>
Name of attribute9 that needs to be sent in SAML Assertion

<b>Attribute9Expr</b>
Expression that will be evaluated to obtain attribute9's value to be sent in Assertion

<b>Attribute9FriendlyName</b>
User-Friendly Name of attribute9 that needs to be sent in SAML Assertion

<b>Attribute9Format</b>
Format of Attribute9 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute10</b>
Name of attribute10 that needs to be sent in SAML Assertion

<b>Attribute10Expr</b>
Expression that will be evaluated to obtain attribute10's value to be sent in Assertion

<b>Attribute10FriendlyName</b>
User-Friendly Name of attribute10 that needs to be sent in SAML Assertion

<b>Attribute10Format</b>
Format of Attribute10 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute11</b>
Name of attribute11 that needs to be sent in SAML Assertion

<b>Attribute11Expr</b>
Expression that will be evaluated to obtain attribute11's value to be sent in Assertion

<b>Attribute11FriendlyName</b>
User-Friendly Name of attribute11 that needs to be sent in SAML Assertion

<b>Attribute11Format</b>
Format of Attribute11 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute12</b>
Name of attribute12 that needs to be sent in SAML Assertion

<b>Attribute12Expr</b>
Expression that will be evaluated to obtain attribute12's value to be sent in Assertion

<b>Attribute12FriendlyName</b>
User-Friendly Name of attribute12 that needs to be sent in SAML Assertion

<b>Attribute12Format</b>
Format of Attribute12 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute13</b>
Name of attribute13 that needs to be sent in SAML Assertion

<b>Attribute13Expr</b>
Expression that will be evaluated to obtain attribute13's value to be sent in Assertion

<b>Attribute13FriendlyName</b>
User-Friendly Name of attribute13 that needs to be sent in SAML Assertion

<b>Attribute13Format</b>
Format of Attribute13 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute14</b>
Name of attribute14 that needs to be sent in SAML Assertion

<b>Attribute14Expr</b>
Expression that will be evaluated to obtain attribute14's value to be sent in Assertion

<b>Attribute14FriendlyName</b>
User-Friendly Name of attribute14 that needs to be sent in SAML Assertion

<b>Attribute14Format</b>
Format of Attribute14 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute15</b>
Name of attribute15 that needs to be sent in SAML Assertion

<b>Attribute15Expr</b>
Expression that will be evaluated to obtain attribute15's value to be sent in Assertion

<b>Attribute15FriendlyName</b>
User-Friendly Name of attribute15 that needs to be sent in SAML Assertion

<b>Attribute15Format</b>
Format of Attribute15 to be sent in Assertion.
Possible values: URI, Basic

<b>Attribute16</b>
Name of attribute16 that needs to be sent in SAML Assertion

<b>Attribute16Expr</b>
Expression that will be evaluated to obtain attribute16's value to be sent in Assertion

<b>Attribute16FriendlyName</b>
User-Friendly Name of attribute16 that needs to be sent in SAML Assertion

<b>Attribute16Format</b>
Format of Attribute16 to be sent in Assertion.
Possible values: URI, Basic

<b>encryptAssertion</b>
Option to encrypt assertion when Netscaler IDP sends one.
Possible values: ON, OFF
Default value: OFF

<b>encryptionAlgorithm</b>
Algorithm to be used to encrypt SAML assertion
Possible values: DES3, AES128, AES192, AES256
Default value: AES256



##unset authentication samlIdPProfile

Use this command to remove authentication samlIdPProfile settings.Refer to the set authentication samlIdPProfile command for meanings of the arguments.


##Synopsys

unset authentication samlIdPProfile &lt;name> [-samlSPCertName] [-samlIdPCertName] [-assertionConsumerServiceURL] [-sendPassword] [-samlIssuerName] [-rejectUnsignedRequests] [-signatureAlg] [-digestMethod] [-audience] [-NameIDFormat] [-NameIDExpr] [-Attribute1] [-Attribute1FriendlyName] [-Attribute1Format] [-Attribute2] [-Attribute2FriendlyName] [-Attribute2Format] [-Attribute3] [-Attribute3FriendlyName] [-Attribute3Format] [-Attribute4] [-Attribute4FriendlyName] [-Attribute4Format] [-Attribute5] [-Attribute5FriendlyName] [-Attribute5Format] [-Attribute6] [-Attribute6FriendlyName] [-Attribute6Format] [-Attribute7] [-Attribute7FriendlyName] [-Attribute7Format] [-Attribute8] [-Attribute8FriendlyName] [-Attribute8Format] [-Attribute9] [-Attribute9FriendlyName] [-Attribute9Format] [-Attribute10] [-Attribute10FriendlyName] [-Attribute10Format] [-Attribute11] [-Attribute11FriendlyName] [-Attribute11Format] [-Attribute12] [-Attribute12FriendlyName] [-Attribute12Format] [-Attribute13] [-Attribute13FriendlyName] [-Attribute13Format] [-Attribute14] [-Attribute14FriendlyName] [-Attribute14Format] [-Attribute15] [-Attribute15FriendlyName] [-Attribute15Format] [-Attribute16] [-Attribute16FriendlyName] [-Attribute16Format] [-encryptAssertion] [-encryptionAlgorithm]


##show authentication samlIdPProfile

Displays information about all configured saml single sign-on profiles, or displays detailed information about the specified action.


##Synopsys

show authentication samlIdPProfile [&lt;name>]


##Arguments

<b>name</b>
Name for the new saml single sign-on profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after an action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').



##Outputs

<b>samlSPCertName</b>
Name of the SSL certificate of SAML Relying Party. This certificate is used to verify signature of the incoming AuthnRequest from a Relying Party or Service Provider

<b>samlIdPCertName</b>
Name of the signing authority as given in the SAML server's SSL certificate. This certificate is used to sign the SAMLResposne that is sent to Relying Party or Service Provider after successful authentication

<b>assertionConsumerServiceURL</b>
URL to which the assertion is to be sent.

<b>sendPassword</b>
Option to send password in assertion.

<b>samlIssuerName</b>
The name to be used in requests sent from	Netscaler to IdP to uniquely identify Netscaler.

<b>rejectUnsignedRequests</b>
Option to Reject unsigned SAML Requests.

<b>signatureAlg</b>
Algorithm to be used to sign/verify SAML transactions

<b>digestMethod</b>
Algorithm to be used to compute/verify digest for SAML transactions

<b>audience</b>
Audience for which assertion sent by IdP is applicable. This is typically entity name or url that represents ServiceProvider

<b>NameIDFormat</b>
Format of Name Identifier sent in Assertion.

<b>NameIDExpr</b>
Expression that will be evaluated to obtain NameIdentifier to be sent in assertion

<b>Attribute1</b>
Name of attribute1 that needs to be sent in SAML Assertion

<b>Attribute2</b>
Name of attribute2 that needs to be sent in SAML Assertion

<b>Attribute3</b>
Name of attribute3 that needs to be sent in SAML Assertion

<b>Attribute4</b>
Name of attribute4 that needs to be sent in SAML Assertion

<b>Attribute5</b>
Name of attribute5 that needs to be sent in SAML Assertion

<b>Attribute6</b>
Name of attribute6 that needs to be sent in SAML Assertion

<b>Attribute7</b>
Name of attribute7 that needs to be sent in SAML Assertion

<b>Attribute8</b>
Name of attribute8 that needs to be sent in SAML Assertion

<b>Attribute9</b>
Name of attribute9 that needs to be sent in SAML Assertion

<b>Attribute10</b>
Name of attribute10 that needs to be sent in SAML Assertion

<b>Attribute11</b>
Name of attribute11 that needs to be sent in SAML Assertion

<b>Attribute12</b>
Name of attribute12 that needs to be sent in SAML Assertion

<b>Attribute13</b>
Name of attribute13 that needs to be sent in SAML Assertion

<b>Attribute14</b>
Name of attribute14 that needs to be sent in SAML Assertion

<b>Attribute15</b>
Name of attribute15 that needs to be sent in SAML Assertion

<b>Attribute16</b>
Name of attribute16 that needs to be sent in SAML Assertion

<b>Attribute1FriendlyName</b>
User-Friendly Name of attribute1 that needs to be sent in SAML Assertion

<b>Attribute2FriendlyName</b>
User-Friendly Name of attribute2 that needs to be sent in SAML Assertion

<b>Attribute3FriendlyName</b>
User-Friendly Name of attribute3 that needs to be sent in SAML Assertion

<b>Attribute4FriendlyName</b>
User-Friendly Name of attribute4 that needs to be sent in SAML Assertion

<b>Attribute5FriendlyName</b>
User-Friendly Name of attribute5 that needs to be sent in SAML Assertion

<b>Attribute6FriendlyName</b>
User-Friendly Name of attribute6 that needs to be sent in SAML Assertion

<b>Attribute7FriendlyName</b>
User-Friendly Name of attribute7 that needs to be sent in SAML Assertion

<b>Attribute8FriendlyName</b>
User-Friendly Name of attribute8 that needs to be sent in SAML Assertion

<b>Attribute9FriendlyName</b>
User-Friendly Name of attribute9 that needs to be sent in SAML Assertion

<b>Attribute10FriendlyName</b>
User-Friendly Name of attribute10 that needs to be sent in SAML Assertion

<b>Attribute11FriendlyName</b>
User-Friendly Name of attribute11 that needs to be sent in SAML Assertion

<b>Attribute12FriendlyName</b>
User-Friendly Name of attribute12 that needs to be sent in SAML Assertion

<b>Attribute13FriendlyName</b>
User-Friendly Name of attribute13 that needs to be sent in SAML Assertion

<b>Attribute14FriendlyName</b>
User-Friendly Name of attribute14 that needs to be sent in SAML Assertion

<b>Attribute15FriendlyName</b>
User-Friendly Name of attribute15 that needs to be sent in SAML Assertion

<b>Attribute16FriendlyName</b>
User-Friendly Name of attribute16 that needs to be sent in SAML Assertion

<b>Attribute1Format</b>
Format of Attribute1 to be sent in Assertion.

<b>Attribute2Format</b>
Format of Attribute2 to be sent in Assertion.

<b>Attribute3Format</b>
Format of Attribute3 to be sent in Assertion.

<b>Attribute4Format</b>
Format of Attribute4 to be sent in Assertion.

<b>Attribute5Format</b>
Format of Attribute5 to be sent in Assertion.

<b>Attribute6Format</b>
Format of Attribute6 to be sent in Assertion.

<b>Attribute7Format</b>
Format of Attribute7 to be sent in Assertion.

<b>Attribute8Format</b>
Format of Attribute8 to be sent in Assertion.

<b>Attribute9Format</b>
Format of Attribute9 to be sent in Assertion.

<b>Attribute10Format</b>
Format of Attribute10 to be sent in Assertion.

<b>Attribute11Format</b>
Format of Attribute11 to be sent in Assertion.

<b>Attribute12Format</b>
Format of Attribute12 to be sent in Assertion.

<b>Attribute13Format</b>
Format of Attribute13 to be sent in Assertion.

<b>Attribute14Format</b>
Format of Attribute14 to be sent in Assertion.

<b>Attribute15Format</b>
Format of Attribute15 to be sent in Assertion.

<b>Attribute16Format</b>
Format of Attribute16 to be sent in Assertion.

<b>Attribute1Expr</b>
Expression that will be evaluated to obtain attribute1's value to be sent in Assertion

<b>Attribute2Expr</b>
Expression that will be evaluated to obtain attribute2's value to be sent in Assertion

<b>Attribute3Expr</b>
Expression that will be evaluated to obtain attribute3's value to be sent in Assertion

<b>Attribute4Expr</b>
Expression that will be evaluated to obtain attribute4's value to be sent in Assertion

<b>Attribute5Expr</b>
Expression that will be evaluated to obtain attribute5's value to be sent in Assertion

<b>Attribute6Expr</b>
Expression that will be evaluated to obtain attribute6's value to be sent in Assertion

<b>Attribute7Expr</b>
Expression that will be evaluated to obtain attribute7's value to be sent in Assertion

<b>Attribute8Expr</b>
Expression that will be evaluated to obtain attribute8's value to be sent in Assertion

<b>Attribute9Expr</b>
Expression that will be evaluated to obtain attribute9's value to be sent in Assertion

<b>Attribute10Expr</b>
Expression that will be evaluated to obtain attribute10's value to be sent in Assertion

<b>Attribute11Expr</b>
Expression that will be evaluated to obtain attribute11's value to be sent in Assertion

<b>Attribute12Expr</b>
Expression that will be evaluated to obtain attribute12's value to be sent in Assertion

<b>Attribute13Expr</b>
Expression that will be evaluated to obtain attribute13's value to be sent in Assertion

<b>Attribute14Expr</b>
Expression that will be evaluated to obtain attribute14's value to be sent in Assertion

<b>Attribute15Expr</b>
Expression that will be evaluated to obtain attribute15's value to be sent in Assertion

<b>Attribute16Expr</b>
Expression that will be evaluated to obtain attribute16's value to be sent in Assertion

<b>encryptAssertion</b>
Option to encrypt assertion when Netscaler IDP sends one.

<b>encryptionAlgorithm</b>
Algorithm to be used to encrypt SAML assertion

<b>devno</b>

<b>count</b>

<b>stateflag</b>



