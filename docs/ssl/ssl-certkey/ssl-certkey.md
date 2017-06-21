#ssl certKey

The following operations can be performed on "ssl certKey":


[add](#add-ssl-certkey) | [rm](#rm-ssl-certkey) | [set](#set-ssl-certkey) | [unset](#unset-ssl-certkey) | [bind](#bind-ssl-certkey) | [unbind](#unbind-ssl-certkey) | [link](#link-ssl-certkey) | [unlink](#unlink-ssl-certkey) | [show](#show-ssl-certkey) | [update](#update-ssl-certkey)

##add ssl certKey

Adds a certificate-key pair to memory. After it is bound to a virtual server or service, it is used for processing SSL transactions.In a high-availability configuration, the path to the certificate and the optional private key must be the same on the primary and the secondary appliance. For a server certificate, a private key is required.


##Synopsys

add ssl certKey &lt;certkeyName> (-cert &lt;string>  [-password]) [-key &lt;string> | -fipsKey &lt;string> | -hsmKey &lt;string>] [-inform &lt;inform>] [-expiryMonitor ( ENABLED | DISABLED )  [-notificationPeriod &lt;positive_integer>]] [-bundle ( YES | NO )]


##Arguments

<b>certkeyName</b>
Name for the certificate and private-key pair. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the certificate-key pair is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my cert" or 'my cert').

<b>cert</b>
Name of and, optionally, path to the X509 certificate file that is used to form the certificate-key pair. The certificate file should be present on the appliance's hard-disk drive or solid-state drive. Storing a certificate in any location other than the default might cause inconsistency in a high availability setup. /nsconfig/ssl/ is the default path.

<b>key</b>
Name of and, optionally, path to the private-key file that is used to form the certificate-key pair. The certificate file should be present on the appliance's hard-disk drive or solid-state drive. Storing a certificate in any location other than the default might cause inconsistency in a high availability setup. /nsconfig/ssl/ is the default path.

<b>password</b>
Passphrase that was used to encrypt the private-key. Use this option to load encrypted private-keys in PEM format.

<b>fipsKey</b>
Name of the FIPS key that was created inside the Hardware Security Module (HSM) of a FIPS appliance, or a key that was imported into the HSM.

<b>hsmKey</b>
Name of the HSM key that was created in the External Hardware Security Module (HSM) of a FIPS appliance.

<b>inform</b>
Input format of the certificate and the private-key files. The three formats supported by the appliance are:
PEM - Privacy Enhanced Mail
DER - Distinguished Encoding Rule
PFX - Personal Information Exchange
Possible values: DER, PEM, PFX
Default value: PEM

<b>passplain</b>
Pass phrase used to encrypt the private-key. Required when adding an encrypted private-key in PEM format.

<b>expiryMonitor</b>
Issue an alert when the certificate is about to expire.
Possible values: ENABLED, DISABLED

<b>notificationPeriod</b>
Time, in number of days, before certificate expiration, at which to generate an alert that the certificate is about to expire.
Minimum value: 10
Maximum value: 100

<b>bundle</b>
Parse the certificate chain as a single file after linking the server certificate to its issuer's certificate within the file.
Possible values: YES, NO
Default value: NO



##Example

1)	add ssl certkey siteAcertkey -cert /nsconfig/ssl/cert.pem -key /nsconfig/ssl/pkey.pemThe above command loads a certificate and private key file.2)	add ssl certkey siteAcertkey -cert /nsconfig/ssl/cert.pem -key /nsconfig/ssl/pkey.pem -passwordPassword: ********The above command loads a certificate and private key file. Here the private key file is an encrypted key.3)	add ssl certkey fipscert -cert /nsconfig/ssl/cert.pem -fipskey fips1024The above command loads a certificate and associates it with the corresponding FIPS key that resides within the HSM.4)	add ssl certkey externalhsmcert -cert /nsconfig/ssl/hsmcert.pem -hsmkey key_simple_rsa1The above command loads a certificate and associates it with the corresponding HSM key that resides within the External HSM.

##rm ssl certKey

Removes all the certificate-key pairs, or the specified certificate-key pair, from the appliance. The certificate-key pair is removed only if it is not referenced by any other object. The reference count is updated when the certificate-key pair is bound to an SSL virtual server or linked to another certificate-key pair.


##Synopsys

rm ssl certKey &lt;certkeyName> ...


##Arguments

<b>certkeyName</b>
Name of the certificate-key pair to remove.



##Example

1)	rm ssl certkey siteAcertkeyThe above command removes the certificate-key pair siteAcertkey from the system.

##set ssl certKey

Modifies the specified attributes of a certificate-key pair.


##Synopsys

set ssl certKey &lt;certkeyName> [-expiryMonitor ( ENABLED | DISABLED )  [-notificationPeriod &lt;positive_integer>]]


##Arguments

<b>certkeyName</b>
Name of the certificate-key pair to modify.

<b>expiryMonitor</b>
Issue an alert when the certificate is about to expire.
Possible values: ENABLED, DISABLED

<b>notificationPeriod</b>
Time, in number of days, before certificate expiration, at which to generate an alert that the certificate is about to expire.
Minimum value: 10
Maximum value: 100



##unset ssl certKey

Use this command to remove ssl certKey settings.Refer to the set ssl certKey command for meanings of the arguments.


##Synopsys

unset ssl certKey &lt;certkeyName> [-expiryMonitor] [-notificationPeriod]


##bind ssl certKey

Binds a certificate-key pair to an SSL virtual server or an SSL service.


##Synopsys

bind ssl certKey [&lt;certkeyName>] [-ocspResponder &lt;string>] [-priority &lt;positive_integer>]


##Arguments

<b>certkeyName</b>
Name of the certificate-key pair.

<b>ocspResponder</b>
Name of the OCSP responder to be associated with the CA certificate.

<b>priority</b>
Priority of the OCSP responder binding.
Minimum value: 1
Maximum value: 32



##Example

1)	bind ssl certkey cacert -ocspResponder ocsp_ca -priority 1In the above example, the CA certificate cacert is bound with the OCSP responder ocsp_ca with priority 1, which is highest.

##Related Commands

<ul><li><a href="../../../w-ssl-vs/w-ssl-vs">show ssl vserver</a></li></ul>



##unbind ssl certKey

Unbinds the specified certificate-key pair from the SSL virtual server or service.


##Synopsys

unbind ssl certKey &lt;certkeyName> -ocspResponder &lt;string>


##Arguments

<b>certkeyName</b>
Name of the certificate-key pair to unbind.

<b>ocspResponder</b>
Name of the OCSP responder.



##Example

1)	unbind ssl certkey sslvip siteAcertkeyIn the above example, the server certificate siteAcertkey is unbound from the SSL virtual server.2) 	unbind ssl certkey sslvip CAcertkey -CAIn the above example, the CA certificate CAcertkey is unbound from the SSL virtual server.

##Related Commands

<ul><li><a href="../../../w-ssl-vs/w-ssl-vs">show ssl vserver</a></li></ul>



##link ssl certKey

Links a certificate-key pair to its Certificate Authority (CA) certificate-key pair.


##Synopsys

link ssl certKey &lt;certkeyName> &lt;linkCertKeyName>


##Arguments

<b>certkeyName</b>
Name of the certificate-key pair to link to its issuer's certificate-key pair in the chain.

<b>linkCertKeyName</b>
Name of the Certificate Authority certificate-key pair to which to link a certificate-key pair.



##Example

1)	link ssl certkey siteAcertkey CAcertkeyIn the above example, the certificate-key siteAcertkey is bound to its issuer certificate-key pair CAcertkey.

##Related Commands

<ul><li><a href="../../../ow-ssl-cer/ow-ssl-cer">show ssl certlink</a></li></ul>



##unlink ssl certKey

Unlinks the certificate-key pair from its Certificate-Authority (CA) certificate-key pair.


##Synopsys

unlink ssl certKey &lt;certkeyName>


##Arguments

<b>certkeyName</b>
Name of the certificate-key pair to unlink.



##Example

1)	unlink ssl certkey siteAcertkeyThe above example unlinks the certificate 'siteAcertkey' from its Certificate-Authority (CA) certificate.

##Related Commands

<ul><li><a href="../../../ow-ssl-cer/ow-ssl-cer">show ssl certlink</a></li></ul>



##show ssl certKey

Displays information about all the certificate-key pairs configured on the appliance, or displays detailed information about the specified certificate-key pair.


##Synopsys

show ssl certKey [&lt;certkeyName>]


##Arguments

<b>certkeyName</b>
Name of the certificate-key pair for which to show detailed information.



##Outputs

<b>cert</b>
The name and location of the file containing the certificate.

<b>key</b>
The name and location of the file containing the key.

<b>inform</b>
The encoding format of the certificate and key (PEM,DER or PFX).

<b>signatureAlg</b>
Signature algorithm.

<b>serial</b>
Serial number.

<b>issuer</b>
Issuer name.

<b>clientCertNotBefore</b>
Not-Before date.

<b>clientCertNotAfter</b>
Not-After date.

<b>daysToExpiration</b>
Days remaining for the certificate to expire.

<b>subject</b>
Subject name.

<b>publickey</b>
Public key algorithm.

<b>publickeysize</b>
Size of the public key.

<b>version</b>
Version.

<b>priority</b>
ocsp priority

<b>status</b>
Status of the certificate.

<b>fipsKey</b>
FIPS key ID.

<b>hsmKey</b>
External HSM key ID.

<b>passcrypt</b>
Passcrypt.

<b>data</b>
Vserver Id

<b>serverName</b>
Vserver name to which the certificate key pair is bound.

<b>serviceName</b>
Service name to which the certificate key pair is bound.

<b>ocspResponder</b>
OCSP responders bound to this certkey

<b>expiryMonitor</b>
Certificate expiry monitor

<b>notificationPeriod</b>
Certificate expiry notification period

<b>linkCertKeyName</b>
The name of the Certificate-Authority.

<b>stateflag</b>

<b>gslbServiceFlag</b>
Indicates that this is a gslb service

<b>devno</b>

<b>count</b>



##Example

1) An example of the output of the show ssl certkey command is shown below:	2 configured certkeys:1)	Name: siteAcertkey	Cert Path: /nsconfig/ssl/siteA-cert.pem	Key Path:  /nsconfig/ssl/siteA-key.pem	Format: PEM	Status: Valid2)	Name: cert1	Cert Path: /nsconfig/ssl/server_cert.pem	Key Path: /nsconfig/ssl/server_key.pem	Format: PEM	Status: Valid2) An example of the output of the show ssl certkey siteAcertkey command is shown below:Name: siteAcertkey		Status: ValidVersion: 3Serial Number: 02Signature Algorithm: md5WithRSAEncryptionIssuer: /C=US/ST=CA/L=Santa Clara/O=siteA/OU=TechValidity	Not Before: Nov 11 14:58:18 2001 GMT	Not After: Aug 7 14:58:18 2004 GMTSubject: /C=US/ST-CA/L=San Jose/O=CA/OU=SecurityPublic Key Algorithm: rsaEncryptionPublic Key size: 1024

##update ssl certKey

Updates the certificate or private key in a certificate-key pair. In a high availability configuration, the path to the certificate and the optional private key must be the same on the primary and secondary nodes.


##Synopsys

update ssl certKey &lt;certkeyName> [-cert &lt;string>  [-password]] [-key &lt;string> | -fipsKey &lt;string>] [-inform &lt;inform>] [-noDomainCheck]


##Arguments

<b>certkeyName</b>
Name of the certificate-key pair to update.

<b>cert</b>
Name of and, optionally, path to the X509 certificate file that is used to form the certificate-key pair. The certificate file should be present on the appliance's hard-disk drive or solid-state drive. Storing a certificate in any location other than the default might cause inconsistency in a high availability setup. /nsconfig/ssl/ is the default path.

<b>key</b>
Name of and, optionally, path to the private-key file that is used to form the certificate-key pair. The certificate file should be present on the appliance's hard-disk drive or solid-state drive. Storing a certificate in any location other than the default might cause inconsistency in a high availability setup. /nsconfig/ssl/ is the default path.

<b>password</b>
Passphrase that was used to encrypt the private-key. Use this option to load encrypted private-keys in PEM format.

<b>fipsKey</b>
Name of the FIPS key that was created inside the Hardware Security Module (HSM) of a FIPS appliance, or a key that was imported into the HSM.

<b>inform</b>
Input format of the certificate and the private-key files. The three formats supported by the appliance are:
PEM - Privacy Enhanced Mail
DER - Distinguished Encoding Rule
PFX - Personal Information Exchange
Possible values: DER, PEM, PFX
Default value: PEM

<b>passplain</b>
Pass phrase used to encrypt the private-key. Required when adding an encrypted private-key in PEM format.

<b>noDomainCheck</b>
Override the check for matching domain names during a certificate update operation.



##Example

1)     update ssl certkey siteAcertkey -cert /nsconfig/ssl/cert.pem -key /nsconfig/ssl/pkey.pemThe above command updates a certificate and private key file.2)      update ssl certkey siteAcertkey -cert /nsconfig/ssl/cert.pem -key /nsconfig/ssl/pkey.pem -passwordPassword: ********The above command updates a certificate and private key file. Here the private key file is an encrypted key.3)	 update ssl certkey mydomaincertThe above command updates the certificate using the same parameters (-cert path/-key path) that it was added with.

##Related Commands

<ul><li><a href="../../../-ssl-ce/-ssl-ce">add ssl certkey</a></li><li><a href="../../../ssl-ce/ssl-ce">rm ssl certkey</a></li></ul>



