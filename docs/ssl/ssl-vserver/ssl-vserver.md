#ssl vserver

The following operations can be performed on "ssl vserver":


[set](#set-ssl-vserver) | [unset](#unset-ssl-vserver) | [bind](#bind-ssl-vserver) | [unbind](#unbind-ssl-vserver) | [show](#show-ssl-vserver)

##set ssl vserver

Sets advanced SSL configuration for an SSL virtual server.


##Synopsys

set ssl vserver &lt;vServerName>@ [-clearTextPort &lt;port>] [-dh ( ENABLED | DISABLED )  -dhFile &lt;string>] [-dhCount &lt;positive_integer>] [-eRSA ( ENABLED | DISABLED )  [-eRSACount &lt;positive_integer>]] [-sessReuse ( ENABLED | DISABLED )  [-sessTimeout &lt;positive_integer>]] [-cipherRedirect ( ENABLED | DISABLED )  [-cipherURL &lt;URL>]] [-sslv2Redirect ( ENABLED | DISABLED )  [-sslv2URL &lt;URL>]] [-clientAuth ( ENABLED | DISABLED )  [-clientCert ( Mandatory | Optional )]] [-sslRedirect ( ENABLED | DISABLED )] [-redirectPortRewrite ( ENABLED | DISABLED )] [-nonFipsCiphers ( ENABLED | DISABLED )] [-ssl2 ( ENABLED | DISABLED )] [-ssl3 ( ENABLED | DISABLED )] [-tls1 ( ENABLED | DISABLED )] [-tls11 ( ENABLED | DISABLED )] [-tls12 ( ENABLED | DISABLED )] [-SNIEnable ( ENABLED | DISABLED )] [-pushEncTrigger &lt;pushEncTrigger>] [-sendCloseNotify ( YES | NO )] [-dtlsProfileName &lt;string>] [-sslProfile &lt;string>]


##Arguments

<b>vServerName</b>
Name of the SSL virtual server for which to set advanced configuration.

<b>clearTextPort</b>
Port on which clear-text data is sent by the appliance to the server. Do not specify this parameter for SSL offloading with end-to-end encryption.
Default value: 0

<b>dh</b>
State of Diffie-Hellman (DH) key exchange.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dhCount</b>
Number of interactions, between the client and the NetScaler appliance, after which the DH private-public pair is regenerated. A value of zero (0) specifies infinite use (no refresh).
Maximum value: 65534

<b>eRSA</b>
State of Ephemeral RSA (eRSA) key exchange. Ephemeral RSA allows clients that support only export ciphers to communicate with the secure server even if the server certificate does not support export clients. The ephemeral RSA key is automatically generated when you bind an export cipher to an SSL or TCP-based SSL virtual server or service. When you remove the export cipher, the eRSA key is not deleted. It is reused at a later date when another export cipher is bound to an SSL or TCP-based SSL virtual server or service. The eRSA key is deleted when the appliance restarts.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>sessReuse</b>
State of session reuse. Establishing the initial handshake requires CPU-intensive public key encryption operations. With the ENABLED setting, session key exchange is avoided for session resumption requests received from the client.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>cipherRedirect</b>
State of Cipher Redirect. If cipher redirect is enabled, you can configure an SSL virtual server or service to display meaningful error messages if the SSL handshake fails because of a cipher mismatch between the virtual server or service and the client.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>sslv2Redirect</b>
State of SSLv2 Redirect. If SSLv2 redirect is enabled, you can configure an SSL virtual server or service to display meaningful error messages if the SSL handshake fails because of a protocol version mismatch between the virtual server or service and the client.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>clientAuth</b>
State of client authentication. If client authentication is enabled, the virtual server terminates the SSL handshake if the SSL client does not provide a valid certificate.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>sslRedirect</b>
State of HTTPS redirects for the SSL virtual server. 
For an SSL session, if the client browser receives a redirect message, the browser tries to connect to the new location. However, the secure SSL session breaks if the object has moved from a secure site (https://) to an unsecure site (http://). Typically, a warning message appears on the screen, prompting the user to continue or disconnect.
If SSL Redirect is ENABLED, the redirect message is automatically converted from http:// to https:// and the SSL session does not break.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>redirectPortRewrite</b>
State of the port rewrite while performing HTTPS redirect. If this parameter is ENABLED and the URL from the server does not contain the standard port, the port is rewritten to the standard.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>nonFipsCiphers</b>
State of usage of non-FIPS approved ciphers. Valid only for an SSL service bound with a FIPS key and certificate.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>ssl2</b>
State of SSLv2 protocol support for the SSL Virtual Server.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>ssl3</b>
State of SSLv3 protocol support for the SSL Virtual Server.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>tls1</b>
State of TLSv1.0 protocol support for the SSL Virtual Server.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>tls11</b>
State of TLSv1.1 protocol support for the SSL Virtual Server. TLSv1.1 protocol is supported only on the MPX appliance. Support is not available on a FIPS appliance or on a NetScaler VPX virtual appliance. On an SDX appliance, TLSv1.1 protocol is supported only if an SSL chip is assigned to the instance.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>tls12</b>
State of TLSv1.2 protocol support for the SSL Virtual Server. TLSv1.2 protocol is supported only on the MPX appliance. Support is not available on a FIPS appliance or on a NetScaler VPX virtual appliance. On an SDX appliance, TLSv1.2 protocol is supported only if an SSL chip is assigned to the instance.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>SNIEnable</b>
State of the Server Name Indication (SNI) feature on the virtual server and service-based offload. SNI helps to enable SSL encryption on multiple domains on a single virtual server or service if the domains are controlled by the same organization and share the same second-level domain name. For example, *.sports.net can be used to secure domains such as login.sports.net and help.sports.net.
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
SSL profile associated to vserver



##Example

1)	set ssl vserver sslvip -dh ENABLED -dhFile /siteA/dh1024.pem -dhCount 500The above example set the DH parameters for the SSL virtual server 'sslvip'.3)	set ssl vserver sslvip -ssl2 DISABLEDThe above example disables the support for SSLv2 protocol for the SSL virtual server 'sslvip'.

##unset ssl vserver

Use this command to remove ssl vserver settings.Refer to the set ssl vserver command for meanings of the arguments.


##Synopsys

unset ssl vserver &lt;vServerName>@ [-clearTextPort] [-dh] [-dhFile] [-dhCount] [-eRSA] [-eRSACount] [-sessReuse] [-sessTimeout] [-cipherRedirect] [-cipherURL] [-sslv2Redirect] [-sslv2URL] [-clientAuth] [-clientCert] [-sslRedirect] [-redirectPortRewrite] [-nonFipsCiphers] [-ssl2] [-ssl3] [-tls1] [-tls11] [-tls12] [-SNIEnable] [-sendCloseNotify] [-dtlsProfileName] [-sslProfile]


##bind ssl vserver

Binds an SSL certificate-key pair or an SSL policy to an SSL virtual server.


##Synopsys

bind ssl vserver &lt;vServerName>@ ((-policyName &lt;string>  [-priority &lt;positive_integer>]  [-gotoPriorityExpression &lt;expression>]  [-invoke  (&lt;labelType>  &lt;labelName>) ]  ) | ((-certkeyName &lt;string>  [(-CA  [-crlCheck ( Mandatory | Optional ) | -ocspCheck ( Mandatory | Optional )]  [-skipCAName]) | -SNICert] ) | -cipherName &lt;string> | -eccCurveName &lt;eccCurveName>))


##Arguments

<b>vServerName</b>
Name of the SSL virtual server.

<b>policyName</b>
Name of the SSL policy to bind to the SSL virtual server.

<b>certkeyName</b>
Name of the certificate-key pair.

<b>cipherName</b>
Name of the individual cipher, user-defined cipher group, or predefined (built-in) cipher alias.

<b>eccCurveName</b>
Named ECC curve bound to service/vserver.
Possible values: ALL, P_224, P_256, P_384, P_521



##Example

1. bind ssl vserver ssl_vip -certkeyName cert1In the above example the certificate cert1 is bound to the SSL vserver ssl_vip as server certificate.2. bind ssl vserver ssl_vip -certkeyName cert2 -CAIn the above example the certificate cert2 is bound to the SSL vserver ssl_vip as CA certificate.3. bind ssl vserver ssl_vip -certkeyName cert3 -CA -ocspCheck MandatoryIn the above example the certificate cert3 is bound to the SSL vserver ssl_vip as CA certificate, with OCSP check set to Mandatory.4. bind ssl vserver ssl_vip -policyName certInsert_pol -priority 10In the above example the SSL policy certInsert_pol is bound to the SSL vserver ssl_vip with priority 10.

##unbind ssl vserver

Unbinds an SSL policy, cipher, and certificate-key pair from an SSL virtual server.


##Synopsys

unbind ssl vserver &lt;vServerName>@ ((-policyName &lt;string>  [-priority &lt;positive_integer>]) | ((-certkeyName &lt;string>  [-CA | -SNICert] ) | -cipherName &lt;string> | -eccCurveName &lt;eccCurveName>))


##Arguments

<b>vServerName</b>
Name of the SSL virtual server.

<b>policyName</b>
Name of the SSL policy to unbind from the SSL virtual server.

<b>certkeyName</b>
The name of the certificate key pair binding.

<b>cipherName</b>
Name of the cipher.

<b>eccCurveName</b>
Named ECC curve bound to service/vserver.
Possible values: ALL, P_224, P_256, P_384, P_521



##Example

unbind ssl vserver ssl_vip -policyName certInsert_pol

##show ssl vserver

Displays SSL specific configuration information for all SSL virtual servers, or displays detailed information for the specified SSL virtual server.


##Synopsys

show ssl vserver [&lt;vServerName>] [-cipherDetails]


##Arguments

<b>vServerName</b>
Name of the SSL virtual server for which to show detailed information.

<b>cipherDetails</b>
Display details of the individual ciphers bound to the SSL virtual server.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>clearTextPort</b>
The  clearTextPort settings.

<b>dh</b>
The  state  of  Diffie-Hellman (DH) key exchange support.

<b>dhFile</b>
The file name and path for the DH parameter.

<b>dhCount</b>
The  refresh  count  for  the re-generation of DH public-key and private-key from the DH parameter.

<b>eRSA</b>
The state of Ephemeral RSA key exchange support.Ephemeral RSA is used for export ciphers

<b>eRSACount</b>
The  refresh  count  for the re-generation of RSA public-key and private-key pair.

<b>sessReuse</b>
The  state of session re-use support.

<b>sessTimeout</b>
The Session timeout value in seconds.

<b>cipherRedirect</b>
The state of Cipher Redirect feature.Cipher Redirect feature can be used to provide more readable information to SSL clients about mismatch in ciphers between the client and the SSL vserver.

<b>crlCheck</b>
The state of the CRL check parameter. (Mandatory/Optional)

<b>cipherURL</b>
The redirect URL to be used with the Cipher Redirect feature.

<b>sslv2Redirect</b>
The state of SSLv2 Redirect feature. SSLv2 Redirect feature can be used to provide more readable information to SSL client about non-support of SSLv2 protocol on the SSL vserver.

<b>sslv2URL</b>
The  redirect URL to be used with SSLv2 Redirect feature.

<b>clientAuth</b>
The state of Client-Authentication support.

<b>clientCert</b>
The rule for client certificate requirement in client authentication.

<b>sslRedirect</b>
The state of HTTPS redirect feature support.

<b>priority</b>
The priority of the policies bound to this SSL service

<b>polinherit</b>
Whether the bound policy is a inherited policy or not

<b>redirectPortRewrite</b>
The state of port rewrite feature support.

<b>nonFipsCiphers</b>
The state of usage of non FIPS approved ciphers.

<b>ssl2</b>
The  state of SSLv2 protocol support.

<b>ssl3</b>
The state of SSLv3 protocol support.

<b>tls1</b>
The  state of TLSv1.0 protocol support.

<b>tls11</b>
The  state of TLSv1.1 protocol support.

<b>tls12</b>
The  state of TLSv1.2 protocol support.

<b>SNIEnable</b>
The state of SNI extension.Server Name Indication (SNI) helps to enable SSL encryption on multiple subdomains if the domains are controlled by the same organization and share the same second-level domain name. State of SNI feature on service

<b>cipherAliasName/cipherName/cipherGroupName</b>
The name of the cipher group/alias/individual cipheri bindings.

<b>cipherName</b>
The cipher group/alias/individual cipher configuration

<b>description</b>
The cipher suite description.

<b>service</b>
Service

<b>certkeyName</b>
The name of the certificate key pair binding.

<b>policyName</b>
The name of the SSL policy binding.

<b>invoke</b>
Invoke flag. This attribute is relevant only for ADVANCED policies

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE.

<b>serviceName</b>
Service name.

<b>ocspCheck</b>
The state of the OCSP check parameter. (Mandatory/Optional)

<b>pushEncTrigger</b>
PUSH packet triggering encryption: Always, Ignore, Merge

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>CA</b>
CA certificate.

<b>SNICert</b>
The name of the CertKey. Use this option to bind Certkey(s) which will be used in SNI processing.

<b>eccCurveName</b>
Named ECC curve bound to vserver/service.

<b>stateflag</b>

<b>skipCAName</b>
The flag is used to indicate whether this particular CA certificate's CA_Name needs to be sent to the SSL client while requesting for client certificate in a SSL handshake

<b>sendCloseNotify</b>
Enable sending SSL Close-Notify at the end of a transaction

<b>dtlsProfileName</b>
Name of the DTLS profile whose settings are to be applied to the virtual server.

<b>dtlsFlag</b>
The flag is used to indicate whether DTLS is set or not

<b>sslProfile</b>
SSL profile associated to vserver

<b>devno</b>

<b>count</b>



##Example

An example of the output of the show vserver sslvip command is as follows:sh ssl vserver va1        Advanced SSL configuration for VServer va1:        DH: DISABLED        Ephemeral RSA: ENABLED          Refresh Count: 0        Session Reuse: ENABLED          Timeout: 120 seconds        Cipher Redirect: DISABLED        SSLv2 Redirect: DISABLED        ClearText Port: 0        Client Auth: DISABLED        SSL Redirect: DISABLED        Non FIPS Ciphers: DISABLED        SSLv2: DISABLED SSLv3: ENABLED  TLSv1: ENABLED        1 bound certificate:1)      CertKey Name: buy       Server Certificate        1 bound CA certificate:1)      CertKey Name: rtca      CA Certificate        1)      Cipher Name: DEFAULT        Description: Predefined Cipher Alias

##Related Commands

<ul><li><a href="../../../d-ssl-ce/d-ssl-ce">bind ssl certkey</a></li><li><a href="../../../-ssl-c/-ssl-c">bind ssl cipher</a></li></ul>



