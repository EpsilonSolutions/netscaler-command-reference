#ssl vserver

The following operations can be performed on "ssl vserver":


[set](#set-ssl-vserver) | [unset](#unset-ssl-vserver) | [bind](#bind-ssl-vserver) | [unbind](#unbind-ssl-vserver) | [show](#show-ssl-vserver) | [stat](#stat-ssl-vserver)

##set ssl vserver

Sets advanced SSL configuration for an SSL virtual server.


##Synopsys

set ssl vserver &lt;vServerName>@ [-clearTextPort &lt;port>] [-dh ( ENABLED | DISABLED )  -dhFile &lt;string>] [-dhCount &lt;positive_integer>] [-dhKeyExpSizeLimit ( ENABLED | DISABLED )] [-eRSA ( ENABLED | DISABLED )  [-eRSACount &lt;positive_integer>]] [-sessReuse ( ENABLED | DISABLED )  [-sessTimeout &lt;positive_integer>]] [-cipherRedirect ( ENABLED | DISABLED )  [-cipherURL &lt;URL>]] [-sslv2Redirect ( ENABLED | DISABLED )  [-sslv2URL &lt;URL>]] [-clientAuth ( ENABLED | DISABLED )  [-clientCert ( Mandatory | Optional )]] [-sslRedirect ( ENABLED | DISABLED )] [-redirectPortRewrite ( ENABLED | DISABLED )] [-ssl2 ( ENABLED | DISABLED )] [-ssl3 ( ENABLED | DISABLED )] [-tls1 ( ENABLED | DISABLED )] [-tls11 ( ENABLED | DISABLED )] [-tls12 ( ENABLED | DISABLED )] [-SNIEnable ( ENABLED | DISABLED )] [-ocspStapling ( ENABLED | DISABLED )] [-pushEncTrigger &lt;pushEncTrigger>] [-sendCloseNotify ( YES | NO )] [-dtlsProfileName &lt;string>] [-sslProfile &lt;string>] [-HSTS ( ENABLED | DISABLED )] [-maxage &lt;positive_integer>] [-IncludeSubdomains ( YES | NO )] [-strictSigDigestCheck ( ENABLED | DISABLED )]


##Arguments

<b>vServerName</b>
Name of the SSL virtual server for which to set advanced configuration.

<b>clearTextPort</b>
Port on which clear-text data is sent by the appliance to the server. Do not specify this parameter for SSL offloading with end-to-end encryption.
Default value: 0
Maximum value: 65534

<b>dh</b>
State of Diffie-Hellman (DH) key exchange.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dhFile</b>
Name of and, optionally, path to the DH parameter file, in PEM format, to be installed. /nsconfig/ssl/ is the default path.

<b>dhCount</b>
Number of interactions, between the client and the NetScaler appliance, after which the DH private-public pair is regenerated. A value of zero (0) specifies infinite use (no refresh).
Minimum value: 0
Maximum value: 65534

<b>dhKeyExpSizeLimit</b>
This option enables the use of NIST recommended (NIST Special Publication 800-56A) bit size for private-key size. For example, for DH params of size 2048bit, the private-key size recommended is 224bits. This is rounded-up to 256bits.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>eRSA</b>
State of Ephemeral RSA (eRSA) key exchange. Ephemeral RSA allows clients that support only export ciphers to communicate with the secure server even if the server certificate does not support export clients. The ephemeral RSA key is automatically generated when you bind an export cipher to an SSL or TCP-based SSL virtual server or service. When you remove the export cipher, the eRSA key is not deleted. It is reused at a later date when another export cipher is bound to an SSL or TCP-based SSL virtual server or service. The eRSA key is deleted when the appliance restarts.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>eRSACount</b>
Refresh count for regeneration of the RSA public-key and private-key pair. Zero (0) specifies infinite usage (no refresh).
Minimum value: 0
Maximum value: 65534

<b>sessReuse</b>
State of session reuse. Establishing the initial handshake requires CPU-intensive public key encryption operations. With the ENABLED setting, session key exchange is avoided for session resumption requests received from the client.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>sessTimeout</b>
Time, in seconds, for which to keep the session active. Any session resumption request received after the timeout period will require a fresh SSL handshake and establishment of a new SSL session.
Default value: 120
Minimum value: 0
Maximum value: 4294967294

<b>cipherRedirect</b>
State of Cipher Redirect. If cipher redirect is enabled, you can configure an SSL virtual server or service to display meaningful error messages if the SSL handshake fails because of a cipher mismatch between the virtual server or service and the client.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>cipherURL</b>
The redirect URL to be used with the Cipher Redirect feature.

<b>sslv2Redirect</b>
State of SSLv2 Redirect. If SSLv2 redirect is enabled, you can configure an SSL virtual server or service to display meaningful error messages if the SSL handshake fails because of a protocol version mismatch between the virtual server or service and the client.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>sslv2URL</b>
URL of the page to which to redirect the client in case of a protocol version mismatch. Typically, this page has a clear explanation of the error or an alternative location that the transaction can continue from.

<b>clientAuth</b>
State of client authentication. If client authentication is enabled, the virtual server terminates the SSL handshake if the SSL client does not provide a valid certificate.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>clientCert</b>
Type of client authentication. If this parameter is set to MANDATORY, the appliance terminates the SSL handshake if the SSL client does not provide a valid certificate. With the OPTIONAL setting, the appliance requests a certificate from the SSL clients but proceeds with the SSL transaction even if the client presents an invalid certificate.
Caution: Define proper access control policies before changing this setting to Optional.
Possible values: Mandatory, Optional

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

<b>ocspStapling</b>
State of OCSP stapling support on the SSL virtual server. Supported only if the protocol used is higher than SSLv3. Possible values:
ENABLED: The appliance sends a request to the OCSP responder to check the status of the server certificate and caches the response for the specified time. If the response is valid at the time of SSL handshake with the client, the OCSP-based server certificate status is sent to the client during the handshake.
DISABLED: The appliance does not check the status of the server certificate. 
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
Name of the SSL profile that contains SSL settings for the virtual server.

<b>HSTS</b>
State of TLSv1.0 protocol support for the SSL Virtual Server.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>maxage</b>
Set max-age value for STS header
Default value: 0
Minimum value: 0
Maximum value: 4294967294

<b>IncludeSubdomains</b>
Set include sub domain value for STS header
Possible values: YES, NO
Default value: NO

<b>strictSigDigestCheck</b>
Parameter indicating to check whether peer entity certificate during TLS1.2 handshake is signed with one of signature-hash combination supported by Netscaler.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

1)	set ssl vserver sslvip -dh ENABLED -dhFile /siteA/dh1024.pem -dhCount 500The above example set the DH parameters for the SSL virtual server 'sslvip'.3)	set ssl vserver sslvip -ssl2 DISABLEDThe above example disables the support for SSLv2 protocol for the SSL virtual server 'sslvip'.

##unset ssl vserver

Use this command to remove ssl vserver settings.Refer to the set ssl vserver command for meanings of the arguments.


##Synopsys

unset ssl vserver &lt;vServerName>@ [-clearTextPort] [-dh] [-dhFile] [-dhCount] [-dhKeyExpSizeLimit] [-eRSA] [-eRSACount] [-sessReuse] [-sessTimeout] [-cipherRedirect] [-cipherURL] [-sslv2Redirect] [-sslv2URL] [-clientAuth] [-clientCert] [-sslRedirect] [-redirectPortRewrite] [-ssl2] [-ssl3] [-tls1] [-tls11] [-tls12] [-SNIEnable] [-ocspStapling] [-sendCloseNotify] [-dtlsProfileName] [-sslProfile] [-HSTS] [-maxage] [-IncludeSubdomains] [-strictSigDigestCheck]


##bind ssl vserver

Binds an SSL certificate-key pair or an SSL policy to an SSL virtual server.


##Synopsys

bind ssl vserver &lt;vServerName>@ ((-policyName &lt;string>  [-priority &lt;positive_integer>]  [-gotoPriorityExpression &lt;expression>]  [-invoke  (&lt;labelType>  &lt;labelName>) ]  ) | ((-certkeyName &lt;string>  [(-CA  [-crlCheck ( Mandatory | Optional ) | -ocspCheck ( Mandatory | Optional )]  [-skipCAName]) | -SNICert] ) | -cipherName &lt;string> | -eccCurveName &lt;eccCurveName>))


##Arguments

<b>vServerName</b>
Name of the SSL virtual server.

<b>policyName</b>
Name of the SSL policy to bind to the SSL virtual server.

<b>priority</b>
Integer specifying the policy's priority. The lower the number, the higher the priority.
Minimum value: 0
Maximum value: 64000

<b>gotoPriorityExpression</b>
Expression or other value specifying the next policy to be evaluated if the current policy evaluates to TRUE.  Specify one of the following values:
* NEXT - Evaluate the policy with the next higher priority number.
* END - End policy evaluation.
* USE_INVOCATION_RESULT - Applicable if this policy invokes another policy label. If the final goto in the invoked policy label has a value of END, the evaluation stops. If the final goto is anything other than END, the current policy label performs a NEXT.
* A default syntax or classic expression that evaluates to a number.
If you specify an expression, the number to which it evaluates determines the next policy to evaluate, as follows:
* If the expression evaluates to a higher numbered priority, the policy with that priority is evaluated next.
* If the expression evaluates to the priority of the current policy, the policy with the next higher numbered priority is evaluated next.
* If the expression evaluates to a number that is larger than the largest numbered priority, policy evaluation ends.
An UNDEF event is triggered if:
* The expression is invalid.
* The expression evaluates to a priority number that is numerically lower than the current policy's priority.
* The expression evaluates to a priority number that is between the current policy's priority number (say, 30) and the highest priority number (say, 100), but does not match any configured priority number (for example, the expression evaluates to the number 85). This example assumes that the priority number increments by 10 for every successive policy, and therefore a priority number of 85 does not exist in the policy label.
Default value: "END"

<b>invoke</b>
Invoke policies bound to a virtual server, service, or user-defined policy label. After the invoked policies are evaluated, the flow returns to the policy with the next priority.

<b>labelType</b>
Type of policy label to invoke.
Possible values: vserver, service, policylabel

<b>labelName</b>
Name of the policy label, virtual server, or service to invoke if the current policy rule evaluates to TRUE.

<b>certkeyName</b>
Name of the certificate-key pair.

<b>CA</b>
Name of the CA certificate that issues and signs the intermediate-CA certificate or the end-user client or server certificate.

<b>crlCheck</b>
Rule to use for the CRL corresponding to the CA certificate during client authentication. Available settings function as follows:
* MANDATORY - Deny SSL clients if the CRL is missing or expired, or the Next Update date is in the past, or the CRL is incomplete. 
* OPTIONAL - Allow SSL clients if the CRL is missing or expired, or the Next Update date is in the past, or the CRL is incomplete, but deny if the client certificate is revoked in the CRL.
Possible values: Mandatory, Optional
Default value: CRLCHECK_OPTIONAL

<b>skipCAName</b>
The flag is used to indicate whether this particular CA certificates CA Name needs to be sent to the SSL client while requesting for client certificate in a SSL handshake

<b>SNICert</b>
Name of the certificate-key pair to bind for use in SNI processing.

<b>ocspCheck</b>
Rule to use for the OCSP responder associated with the CA certificate during client authentication. If MANDATORY is specified, deny all SSL clients if the OCSP check fails because of connectivity issues with the remote OCSP server, or any other reason that prevents the OCSP check. With the OPTIONAL setting, allow SSL clients even if the OCSP check fails except when the client certificate is revoked.
Possible values: Mandatory, Optional

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

<b>priority</b>
Priority of the NOPOLICY (built-in policy) to be unbound. Not required if you are unbinding a user-defined policy.
Minimum value: 1
Maximum value: 2147483647

<b>certkeyName</b>
The name of the certificate key pair binding.

<b>CA</b>
CA certificate.

<b>SNICert</b>
Name of the SNI certificate-key pair.

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

show ssl vserver [&lt;vServerName>]


##Arguments

<b>vServerName</b>
Name of the SSL virtual server for which to show detailed information.



##Outputs

<b>clearTextPort</b>
The  clearTextPort settings.

<b>dh</b>
The  state  of  Diffie-Hellman (DH) key exchange support.

<b>dhFile</b>
The file name and path for the DH parameter.

<b>dhCount</b>
The  refresh  count  for  the re-generation of DH public-key and private-key from the DH parameter.

<b>dhKeyExpSizeLimit</b>
This option enables the use of NIST recommended (NIST Special Publication 800-56A) bit size for private-key size. For example, for DH params of size 2048bit, the private-key size recommended is 224bits. This is rounded-up to 256bits.

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

<b>type</b>
Bind point to which to bind the policy. Possible Values: HANDSHAKE_REQ, HANDSHAKE_RES, CLIENTHELLO_REQ, CLIENTCERT_REQ, SERVERHELLO_RES, SERVERCERT_RES, SERVERHELLO_DONE_RES and REQUEST. These bindpoints mean:
1. HANDSHAKE_REQ: Policy evaluation will be done at the end of handshake on request side (request side means between client and NetScaler)
2. HANDSHAKE_RES: Policy evaluation will be done at the end of hadnshake on response side (response side means between Netscaler and server)
3. INTERCEPT_REQ: Policy evaluation will be done after receiving Client Hello on request side.
4. CLIENTCERT_REQ: Policy evaluation will be done after receiving Client Certificate on request side.
5. SERVERHELLO_RES: Policy evaluation will be done after receiving Server Hello on response side.
6. SERVERCERT_RES: Policy evaluation will be done after receiving Server Certificate on response side.
7. SERVERHELLO_DONE_RES: Policy evaluation will be done after receiving Server Hello Done on response side.
8. REQUEST: Policy evaluation will be done at appplication above SSL. This bindpoint is default and is used for actions based on clientauth and client cert.

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

<b>ocspStapling</b>
State of OCSP stapling support on the SSL virtual server. Supported only if the protocol used is higher than SSLv3. Possible values:
ENABLED: The appliance sends a request to the OCSP responder to check the status of the server certificate and caches the response for the specified time. If the response is valid at the time of SSL handshake with the client, the OCSP-based server certificate status is sent to the client during the handshake.
DISABLED: The appliance does not check the status of the server certificate.

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
Name of the SSL profile that contains SSL settings for the virtual server.

<b>HSTS</b>
State of TLSv1.0 protocol support for the SSL Virtual Server.

<b>maxage</b>
Set max-age value for STS header

<b>IncludeSubdomains</b>
Set include sub domain value for STS header

<b>strictSigDigestCheck</b>
Parameter indicating to check whether peer entity certificate during TLS1.2 handshake is signed with one of signature-hash combination supported by Netscaler.

<b>devno</b>

<b>count</b>



##Example

An example of the output of the show vserver sslvip command is as follows:sh ssl vserver va1        Advanced SSL configuration for VServer va1:        DH: DISABLED        Ephemeral RSA: ENABLED          Refresh Count: 0        Session Reuse: ENABLED          Timeout: 120 seconds        Cipher Redirect: DISABLED        SSLv2 Redirect: DISABLED        ClearText Port: 0        Client Auth: DISABLED        SSL Redirect: DISABLED        Non FIPS Ciphers: DISABLED        SSLv2: DISABLED SSLv3: ENABLED  TLSv1: ENABLED        1 bound certificate:1)      CertKey Name: buy       Server Certificate        1 bound CA certificate:1)      CertKey Name: rtca      CA Certificate        1)      Cipher Name: DEFAULT        Description: Predefined Cipher Alias

##Related Commands

<ul><li><a href="../../../d-ssl-ce/d-ssl-ce">bind ssl certkey</a></li><li><a href="../../../-ssl-c/-ssl-c">bind ssl cipher</a></li></ul>



##stat ssl vserver

Displays statistics for all SSL virtual servers, or displays detailed statistics for the specified SSL virtual server.


##Synopsys

stat ssl vserver [&lt;vServerName>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>vServerName</b>
Name of the SSL virtual server for which to show detailed statistics

<b>detail</b>
Specifies detailed output (including more statistics). The output can be quite voluminous. Without this argument, the output will show only a summary.

<b>fullValues</b>
Specifies that numbers and strings should be displayed in their full form. Without this option, long strings are shortened and large numbers are abbreviated

<b>ntimes</b>
The number of times, in intervals of seven seconds, the statistics should be displayed.
Default value: 1
Minimum value: 0

<b>logFile</b>
The name of the log file to be used as input.

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>Vserver Health (Health)</b>
Health of the vserver. This gives percentage of UP services bound to this vserver.

<b>Vserver IP address (vsvrIP)</b>
IP address of the vserver

<b>Port (port)</b>
The port on which the service is running.

<b>Vserver protocol (Protocol)</b>
Protocol associated with the vserver

<b>State</b>
Current state of the server. Possible values are UP, DOWN, UNKNOWN, OFS(Out of Service), TROFS(Transition Out of Service), TROFS_DOWN(Down When going Out of Service)

<b>total ACTIVE services (actSvcs)</b>
number of ACTIVE services bound to a vserver

<b>Client Authentication Success (sslTotClientAuthSuccess)</b>
Number of successful client authentication on this vserver

<b>Client Authentication Failure (sslTotClientAuthFailure)</b>
Number of failure client authentication on this vserver

<b>Total encrypted bytes (sslCtxTotEncBytes)</b>
Number of encrypted bytes per SSL vserver

<b>Total decrypted bytes (sslCtxTotDecBytes)</b>
Number of decrypted bytes per SSL vserver

<b>Total hardware encrypted bytes (sslCtxTotHwEncBytes)</b>
Number of hardware encrypted bytes per SSL vserver

<b>Total hardware decrypted bytes (sslCtxTotHwDec_Bytes)</b>
Number of hw decrypted bytes per SSL vserver

<b>Total new sessions created (sslCtxTotSessionNew)</b>
Number of new sessions created

<b>Total session hits (sslCtxTotSessionHits)</b>
Number of session hits



##Related Commands

<ul><li><a href="../../..//">stat ssl</a></li></ul>



