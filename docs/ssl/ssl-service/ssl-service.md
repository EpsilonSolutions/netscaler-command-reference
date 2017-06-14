#ssl service

The following operations can be performed on "ssl service":


[set](#set-ssl-service) | [unset](#unset-ssl-service) | [bind](#bind-ssl-service) | [unbind](#unbind-ssl-service) | [show](#show-ssl-service)

##set ssl service

Sets the advanced SSL configuration for an SSL service.


##Synopsys

set ssl service &lt;serviceName>@ [-dh ( ENABLED | DISABLED )  -dhFile &lt;string>] [-dhCount &lt;positive_integer>] [-eRSA ( ENABLED | DISABLED )  [-eRSACount &lt;positive_integer>]] [-sessReuse ( ENABLED | DISABLED )  [-sessTimeout &lt;positive_integer>]] [-cipherRedirect ( ENABLED | DISABLED )  [-cipherURL &lt;URL>]] [-sslv2Redirect ( ENABLED | DISABLED )  [-sslv2URL &lt;URL>]] [-clientAuth ( ENABLED | DISABLED )  [-clientCert ( Mandatory | Optional )]] [-sslRedirect ( ENABLED | DISABLED )] [-redirectPortRewrite ( ENABLED | DISABLED )] [-nonFipsCiphers ( ENABLED | DISABLED )] [-ssl2 ( ENABLED | DISABLED )] [-ssl3 ( ENABLED | DISABLED )] [-tls1 ( ENABLED | DISABLED )] [-tls11 ( ENABLED | DISABLED )] [-tls12 ( ENABLED | DISABLED )] [-SNIEnable ( ENABLED | DISABLED )] [-serverAuth ( ENABLED | DISABLED )  [-commonName &lt;string>]] [-pushEncTrigger &lt;pushEncTrigger>] [-sendCloseNotify ( YES | NO )] [-dtlsProfileName &lt;string>] [-sslProfile &lt;string>]


##Arguments

<b>serviceName</b>
Name of the SSL service.

<b>dh</b>
State of Diffie-Hellman (DH) key exchange. This parameter is not applicable when configuring a backend service.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dhCount</b>
Number of interactions, between the client and the NetScaler appliance, after which the DH private-public pair is regenerated. A value of zero (0) specifies infinite use (no refresh). This parameter is not applicable when configuring a backend service.
Maximum value: 65534

<b>eRSA</b>
State of Ephemeral RSA (eRSA) key exchange. Ephemeral RSA allows clients that support only export ciphers to communicate with the secure server even if the server certificate does not support export clients. The ephemeral RSA key is automatically generated when you bind an export cipher to an SSL or TCP-based SSL virtual server or service. When you remove the export cipher, the eRSA key is not deleted. It is reused at a later date when another export cipher is bound to an SSL or TCP-based SSL virtual server or service. The eRSA key is deleted when the appliance restarts.
This parameter is not applicable when configuring a backend service.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>sessReuse</b>
State of session reuse. Establishing the initial handshake requires CPU-intensive public key encryption operations. With the ENABLED setting, session key exchange is avoided for session resumption requests received from the client.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>cipherRedirect</b>
State of Cipher Redirect. If this parameter is set to ENABLED, you can configure an SSL virtual server or service to display meaningful error messages if the SSL handshake fails because of a cipher mismatch between the virtual server or service and the client.
This parameter is not applicable when configuring a backend service.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>sslv2Redirect</b>
State of SSLv2 Redirect. If this parameter is set to ENABLED, you can configure an SSL virtual server or service to display meaningful error messages if the SSL handshake fails because of a protocol version mismatch between the virtual server or service and the client.
This parameter is not applicable when configuring a backend service.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>clientAuth</b>
State of client authentication. In service-based SSL offload, the service terminates the SSL handshake if the SSL client does not provide a valid certificate. 
This parameter is not applicable when configuring a backend service.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>sslRedirect</b>
State of HTTPS redirects for the SSL service. 
For an SSL session, if the client browser receives a redirect message, the browser tries to connect to the new location. However, the secure SSL session breaks if the object has moved from a secure site (https://) to an unsecure site (http://). Typically, a warning message appears on the screen, prompting the user to continue or disconnect.
If SSL Redirect is ENABLED, the redirect message is automatically converted from http:// to https:// and the SSL session does not break.
This parameter is not applicable when configuring a backend service.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>redirectPortRewrite</b>
State of the port rewrite while performing HTTPS redirect. If this parameter is set to ENABLED, and the URL from the server does not contain the standard port, the port is rewritten to the standard.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>nonFipsCiphers</b>
State of usage of ciphers that are not FIPS approved. Valid only for an SSL service bound with a FIPS key and certificate.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>ssl2</b>
State of SSLv2 protocol support for the SSL service.
This parameter is not applicable when configuring a backend service.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>ssl3</b>
State of SSLv3 protocol support for the SSL service.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>tls1</b>
State of TLSv1.0 protocol support for the SSL service.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>tls11</b>
State of TLSv1.1 protocol support for the SSL service.Enabled for Front-end service on MPX-CVM platform only.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>tls12</b>
State of TLSv1.2 protocol support for the SSL service.Enabled for Front-end service on MPX-CVM platform only.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>SNIEnable</b>
State of the Server Name Indication (SNI) feature on the virtual server and service-based offload. SNI helps to enable SSL encryption on multiple domains on a single virtual server or service if the domains are controlled by the same organization and share the same second-level domain name. For example, *.sports.net can be used to secure domains such as login.sports.net and help.sports.net.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>serverAuth</b>
State of server authentication support for the SSL service.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>pushEncTrigger</b>
Trigger encryption on the basis of the PUSH flag value. Available settings function as follows:
* ALWAYS - Any PUSH packet triggers encryption.
* IGNORE - Ignore PUSH packet for triggering encryption.
* MERGE - For a consecutive sequence of PUSH packets, the last PUSH packet triggers encryption.
* TIMER - PUSH packet triggering encryption is delayed by the time defined in the set ssl parameter command or in the Change Advanced SSL Settings dialog box.
Possible values: Always, Merge, Ignore, Timer

<b>sendCloseNotify</b>
Enable sending SSL Close-Notify at the end of a transaction
Possible values: YES, NO
Default value: YES

<b>dtlsProfileName</b>
Name of the DTLS profile whose settings are to be applied to the virtual server.

<b>sslProfile</b>
SSL profile associated to service



##Example

1)	set ssl service sslsvc -dh ENABLED -dhFile /nsconfig/ssl/dh1024.pem -dhCount 500The above example sets the DH parameters for the SSL service 'sslsvc'.2.	set ssl service sslsvc -ssl2 DISABLEDThe above example disables the support for SSLv2 protocol for the SSL service 'sslsvc'.

##unset ssl service

Use this command to remove ssl service settings.Refer to the set ssl service command for meanings of the arguments.


##Synopsys

unset ssl service &lt;serviceName>@ [-dh] [-dhFile] [-dhCount] [-eRSA] [-eRSACount] [-sessReuse] [-sessTimeout] [-cipherRedirect] [-cipherURL] [-sslv2Redirect] [-sslv2URL] [-clientAuth] [-clientCert] [-sslRedirect] [-redirectPortRewrite] [-nonFipsCiphers] [-ssl2] [-ssl3] [-tls1] [-tls11] [-tls12] [-SNIEnable] [-serverAuth] [-commonName] [-sendCloseNotify] [-dtlsProfileName] [-sslProfile]


##bind ssl service

Binds an SSL certificate-key pair or an SSL policy to a transparent SSL service.


##Synopsys

bind ssl service &lt;serviceName>@ ((-policyName &lt;string>  [-priority &lt;positive_integer>]  [-gotoPriorityExpression &lt;expression>]  [-invoke  (&lt;labelType>  &lt;labelName>) ]  ) | ((-certkeyName &lt;string>  [(-CA  [-crlCheck ( Mandatory | Optional ) | -ocspCheck ( Mandatory | Optional )]  [-skipCAName]) | -SNICert] ) | -cipherName &lt;string> | -eccCurveName &lt;eccCurveName>))


##Arguments

<b>serviceName</b>
Name of the SSL service for which to set advanced configuration.

<b>policyName</b>
Name of the SSL policy to bind to the service.

<b>certkeyName</b>
Name of the certificate-key pair.

<b>cipherName</b>
Name of the individual cipher, user-defined cipher group, or predefined (built-in) cipher alias.

<b>eccCurveName</b>
Named ECC curve bound to service/vserver.
Possible values: ALL, P_224, P_256, P_384, P_521



##Example

bind ssl service ssl_svc -policyName certInsert_pol -priority 10

##unbind ssl service

Unbinds an SSL policy, cipher, and certificate-key pair from an SSL service.


##Synopsys

unbind ssl service &lt;serviceName>@ ((-policyName &lt;string>  [-priority &lt;positive_integer>]) | ((-certkeyName &lt;string>  [(-CA  [-crlCheck ( Mandatory | Optional )]) | -SNICert] ) | -cipherName &lt;string> | -eccCurveName &lt;eccCurveName>))


##Arguments

<b>serviceName</b>
Name of the SSL service.

<b>policyName</b>
Name of the SSL policy to unbind from the SSL service.

<b>certkeyName</b>
The certificate key pair binding.

<b>cipherName</b>
Name of the individual cipher, user-defined cipher group, or predefined (built-in) cipher alias.

<b>eccCurveName</b>
Named ECC curve bound to service/vserver.
Possible values: ALL, P_224, P_256, P_384, P_521



##Example

unbind ssl service ssl_svc -policyName certInsert_pol

##show ssl service

Displays information about SSL-specific configuration information for all SSL services, or displays detailed information about the specified SSL service.


##Synopsys

show ssl service [&lt;serviceName>] [-cipherDetails]


##Arguments

<b>serviceName</b>
Name of the SSL service for which to show detailed information.

<b>cipherDetails</b>
Display details of the individual ciphers bound to the SSL service.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>crlCheck</b>
The state of the CRL check parameter. (Mandatory/Optional)

<b>dh</b>
The  state  of  Diffie-Hellman (DH) key exchange support.

<b>dhFile</b>
The file name and path for the DH parameter.

<b>dhCount</b>
The refresh count for regeneration of DH public-key and private-key  from  the  DH  parameter.

<b>eRSA</b>
The state of Ephemeral RSA key exchange support. Ephemeral RSA is used for export ciphers

<b>eRSACount</b>
The  refresh  count for re-generation of RSA public-key and pri-vate-key pair.

<b>sessReuse</b>
The state of session reuse support.

<b>sessTimeout</b>
The session timeout value in seconds.

<b>cipherRedirect</b>
The state of Cipher Redirect feature.Cipher Redirect feature can be used to provide more readable information to SSL clients about mismatch in ciphers between the client and the SSL vserver.

<b>cipherURL</b>
The redirect URL to be used with the  Cipher  Redirect  feature.

<b>sslv2Redirect</b>
The state of SSLv2 Redirect feature.SSLv2 Redirect feature can be used to provide more readable information to SSL client about non-support of SSLv2 protocol on the SSL vserver.

<b>sslv2URL</b>
The  redirect  URL  to  be used with the SSLv2 Redirect feature.

<b>clientAuth</b>
The state of Client-Authentication support.

<b>clientCert</b>
The rule for client certificate requirement in client authentication.

<b>sslRedirect</b>
The state of HTTPS redirect feature.

<b>redirectPortRewrite</b>
The state of port rewrite feature.

<b>nonFipsCiphers</b>
The state of usage of non FIPS approved ciphers.

<b>ssl2</b>
The state of SSLv2 protocol support.

<b>ssl3</b>
The state of SSLv3 protocol support.

<b>tls1</b>
The state of TLSv1.0 protocol support.

<b>tls11</b>
The state of TLSv1.1 protocol support.

<b>tls12</b>
The state of TLSv1.2 protocol support.

<b>SNIEnable</b>
The state of SNI extension. Server Name Indication (SNI) helps to enable SSL encryption on multiple subdomains if the domains are controlled by the same organization and share the same second-level domain name.

<b>serverAuth</b>
The  state of Server-Authentication support.

<b>commonName</b>
Name to be checked against the CommonName (CN) field in the server certificate bound to the SSL server

<b>cipherAliasName/cipherName/cipherGroupName</b>
The cipher group/alias/individual cipher configuration.

<b>cipherName</b>
The cipher group/alias/individual cipher configuration

<b>description</b>
The cipher suite description.

<b>certkeyName</b>
The certificate key pair binding.

<b>policyName</b>
The SSL policy binding.

<b>invoke</b>
Invoke flag. This attribute is relevant only for ADVANCED policies

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE.

<b>clearTextPort</b>
The clearTextPort settings.

<b>service</b>

<b>priority</b>
The priority of the policies bound to this SSL service

<b>polinherit</b>
Whether the bound policy is a inherited policy or not

<b>ocspCheck</b>
Rule to use for the OCSP responder associated with the CA certificate during client authentication. If MANDATORY is specified, deny all SSL clients if the OCSP check fails because of connectivity issues with the remote OCSP server, or any other reason that prevents the OCSP check. With the OPTIONAL setting, allow SSL clients even if the OCSP check fails except when the client certificate is revoked.

<b>pushEncTrigger</b>
PUSH packet triggering encryption: Always, Ignore, Merge

<b>CA</b>
CA certificate.

<b>SNICert</b>
The name of the CertKey. Use this option to bind Certkey(s) which will be used in SNI processing.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>stateflag</b>

<b>skipCAName</b>
The flag is used to indicate whether this particular CA certificate's CA_Name needs to be sent to the SSL client while requesting      for client certificate in a SSL handshake

<b>sendCloseNotify</b>
Enable sending SSL Close-Notify at the end of a transaction

<b>dtlsProfileName</b>
Name of the DTLS profile whose settings are to be applied to the virtual server.

<b>dtlsFlag</b>
The flag is used to indicate whether DTLS is set or not

<b>eccCurveName</b>
Named ECC curve bound to service/vserver.

<b>sslProfile</b>
SSL profile associated to service

<b>devno</b>

<b>count</b>



##Example

An example of output of show ssl service command is as shown belowshow ssl service svc1        Advanced SSL configuration for Back-end SSL Service svc1:        DH: DISABLED        Ephemeral RSA: ENABLED          Refresh Count: 0        Session Reuse: ENABLED          Timeout: 300 seconds        Cipher Redirect: DISABLED        SSLv2 Redirect: DISABLED        Server Auth: DISABLED        SSL Redirect: DISABLED        Non FIPS Ciphers: DISABLED        SSLv2: DISABLED SSLv3: ENABLED  TLSv1: ENABLED        1)      Cipher Name: ALL        Description: Predefined Cipher Alias

