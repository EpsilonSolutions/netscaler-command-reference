#ssl profile

The following operations can be performed on "ssl profile":


[add](#add-ssl-profile) | [rm](#rm-ssl-profile) | [set](#set-ssl-profile) | [unset](#unset-ssl-profile) | [show](#show-ssl-profile)

##add ssl profile

Add a new SSL profile on the Netscaler


##Synopsys

add ssl profile &lt;name> [-sslProfileType ( BackEnd | FrontEnd )] [-dhCount &lt;positive_integer>] [-dh ( ENABLED | DISABLED )  -dhFile &lt;string>] [-eRSA ( ENABLED | DISABLED )  [-eRSACount &lt;positive_integer>]] [-sessReuse ( ENABLED | DISABLED )  [-sessTimeout &lt;positive_integer>]] [-cipherRedirect ( ENABLED | DISABLED )  [-cipherURL &lt;URL>]] [-clientAuth ( ENABLED | DISABLED )  [-clientCert ( Mandatory | Optional )]] [-sslRedirect ( ENABLED | DISABLED )] [-redirectPortRewrite ( ENABLED | DISABLED )] [-nonFipsCiphers ( ENABLED | DISABLED )] [-ssl3 ( ENABLED | DISABLED )] [-tls1 ( ENABLED | DISABLED )] [-tls11 ( ENABLED | DISABLED )] [-tls12 ( ENABLED | DISABLED )] [-SNIEnable ( ENABLED | DISABLED )] [-serverAuth ( ENABLED | DISABLED )  [-commonName &lt;string>]] [-pushEncTrigger &lt;pushEncTrigger>] [-sendCloseNotify ( YES | NO )] [-clearTextPort &lt;port|*>] [-insertionEncoding ( Unicode | UTF-8 )] [-denySSLReneg &lt;denySSLReneg>] [-quantumSize &lt;quantumSize>] [-strictCAChecks ( YES | NO )] [-encryptTriggerPktCount &lt;positive_integer>] [-pushFlag &lt;positive_integer>] [-dropReqWithNoHostHeader ( YES | NO )] [-pushEncTriggerTimeout &lt;positive_integer>] [-sslTriggerTimeout &lt;positive_integer>]


##Arguments

<b>name</b>
Name of the SSL profile

<b>sslProfileType</b>
Type of SSL profile.FrontEnd is for front end SSL service or vserver.BackEnd is for backend SSL service.
Possible values: BackEnd, FrontEnd
Default value: SSL_FRONTEND

<b>dhCount</b>
Number of interactions, between the client and the NetScaler appliance, after which the DH private-public pair is regenerated. A value of zero (0) specifies infinite use (no refresh). This parameter is not applicable when configuring a backend profile.
Maximum value: 65534

<b>dh</b>
State of Diffie-Hellman (DH) key exchange. This parameter is not applicable when configuring a backend profile.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>eRSA</b>
State of Ephemeral RSA (eRSA) key exchange. Ephemeral RSA allows clients that support only export ciphers to communicate with the secure server even if the server certificate does not support export clients. The ephemeral RSA key is automatically generated when you bind an export cipher to an SSL or TCP-based SSL virtual server or service. When you remove the export cipher, the eRSA key is not deleted. It is reused at a later date when another export cipher is bound to an SSL or TCP-based SSL virtual server or service. The eRSA key is deleted when the appliance restarts.This parameter is not applicable when configuring a backend profile.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>sessReuse</b>
State of session reuse. Establishing the initial handshake requires CPU-intensive public key encryption operations. With the ENABLED setting, session key exchange is avoided for session resumption requests received from the client.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>cipherRedirect</b>
State of Cipher Redirect. If this parameter is set to ENABLED, you can configure an SSL virtual server or service to display meaningful error messages if the SSL handshake fails because of a cipher mismatch between the virtual server or service and the client.This parameter is not applicable when configuring a backend profile.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>clientAuth</b>
State of client authentication. In service-based SSL offload, the service terminates the SSL handshake if the SSL client does not provide a valid certificate. 
This parameter is not applicable when configuring a backend profile.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>sslRedirect</b>
State of HTTPS redirects for the SSL service. 
For an SSL session, if the client browser receives a redirect message, the browser tries to connect to the new location. However, the secure SSL session breaks if the object has moved from a secure site (https://) to an unsecure site (http://). Typically, a warning message appears on the screen, prompting the user to continue or disconnect.
If SSL Redirect is ENABLED, the redirect message is automatically converted from http:// to https:// and the SSL session does not break.
This parameter is not applicable when configuring a backend profile.
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
State of server authentication support for the SSL Backend profile.
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

<b>clearTextPort</b>
The clearTextPort settings.

<b>insertionEncoding</b>
Encoding method used to insert the subject or issuer's name in HTTP requests to servers.
Possible values: Unicode, UTF-8
Default value: UNICODE_INSERTION

<b>denySSLReneg</b>
Deny renegotiation in specified circumstances. Available settings function as follows:
* NO - Allow SSL renegotiation.
* FRONTEND_CLIENT - Deny secure and nonsecure SSL renegotiation initiated by the client.
* FRONTEND_CLIENTSERVER - Deny secure and nonsecure SSL renegotiation initiated by the client or the NetScaler during policy-based client authentication. 
* ALL - Deny all secure and nonsecure SSL renegotiation.
* NONSECURE - Deny nonsecure SSL renegotiation. Allows only clients that support RFC 5746.
Possible values: NO, FRONTEND_CLIENT, FRONTEND_CLIENTSERVER, ALL, NONSECURE
Default value: NORENEG_FE_BE

<b>quantumSize</b>
Amount of data to collect before the data is pushed to the crypto hardware for encryption. For large downloads, a larger quantum size better utilizes the crypto resources.
Possible values: 4096, 8192, 16384
Default value: 8192

<b>strictCAChecks</b>
Enable strict CA certificate checks on the appliance.
Possible values: YES, NO
Default value: NO

<b>encryptTriggerPktCount</b>
Maximum number of queued packets after which encryption is triggered. Use this setting for SSL transactions that send small packets from server to NetScaler.
Default value: 45
Minimum value: 10
Maximum value: 50

<b>pushFlag</b>
Insert PUSH flag into decrypted, encrypted, or all records. If the PUSH flag is set to a value other than 0, the buffered records are forwarded on the basis of the value of the PUSH flag. Available settings function as follows:
0 - Auto (PUSH flag is not set.)
1 - Insert PUSH flag into every decrypted record.
2 -Insert PUSH flag into every encrypted record.
3 - Insert PUSH flag into every decrypted and encrypted record.
Maximum value: 3

<b>dropReqWithNoHostHeader</b>
Host header check for SNI enabled sessions. If this check is enabled and the HTTP request does not contain the host header for SNI enabled sessions, the request is dropped.
Possible values: YES, NO
Default value: NO

<b>pushEncTriggerTimeout</b>
PUSH encryption trigger timeout value. The timeout value is applied only if you set the Push Encryption Trigger parameter to Timer in the SSL virtual server settings.
Default value: 1
Minimum value: 1
Maximum value: 200

<b>sslTriggerTimeout</b>
Time, in milliseconds, after which encryption is triggered for transactions that are not tracked on the NetScaler appliance because their length is not known. There can be a delay of up to 10ms from the specified timeout value before the packet is pushed into the queue.
Default value: 100
Minimum value: 1
Maximum value: 200



##Example

add sslProfile &lt;profile name&gt; -type front

##rm ssl profile

Remove a SSL profile on the Netscaler


##Synopsys

rm ssl profile &lt;name>


##Arguments

<b>name</b>
Name of the SSL profile.



##Example

rm sslProfile &lt;profile name&gt;

##set ssl profile

Set/modify SSL profile values


##Synopsys

set ssl profile &lt;name> [-dh ( ENABLED | DISABLED )  -dhFile &lt;string>  -dhCount &lt;positive_integer>] [-eRSA ( ENABLED | DISABLED )  [-eRSACount &lt;positive_integer>]] [-sessReuse ( ENABLED | DISABLED )  [-sessTimeout &lt;positive_integer>]] [-cipherRedirect ( ENABLED | DISABLED )  [-cipherURL &lt;URL>]] [-clientAuth ( ENABLED | DISABLED )  [-clientCert ( Mandatory | Optional )]] [-sslRedirect ( ENABLED | DISABLED )] [-redirectPortRewrite ( ENABLED | DISABLED )] [-nonFipsCiphers ( ENABLED | DISABLED )] [-ssl3 ( ENABLED | DISABLED )] [-tls1 ( ENABLED | DISABLED )] [-tls11 ( ENABLED | DISABLED )] [-tls12 ( ENABLED | DISABLED )] [-SNIEnable ( ENABLED | DISABLED )] [-serverAuth ( ENABLED | DISABLED )  [-commonName &lt;string>]] [-pushEncTrigger &lt;pushEncTrigger>] [-sendCloseNotify ( YES | NO )] [-clearTextPort &lt;port|*>] [-insertionEncoding ( Unicode | UTF-8 )] [-denySSLReneg &lt;denySSLReneg>] [-quantumSize &lt;quantumSize>] [-strictCAChecks ( YES | NO )] [-encryptTriggerPktCount &lt;positive_integer>] [-pushFlag &lt;positive_integer>] [-dropReqWithNoHostHeader ( YES | NO )] [-pushEncTriggerTimeout &lt;positive_integer>] [-sslTriggerTimeout &lt;positive_integer>]


##Arguments

<b>name</b>
Name of the SSL profile

<b>dh</b>
State of Diffie-Hellman (DH) key exchange. This parameter is not applicable when configuring a backend profile.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>eRSA</b>
State of Ephemeral RSA (eRSA) key exchange. Ephemeral RSA allows clients that support only export ciphers to communicate with the secure server even if the server certificate does not support export clients. The ephemeral RSA key is automatically generated when you bind an export cipher to an SSL or TCP-based SSL virtual server or service. When you remove the export cipher, the eRSA key is not deleted. It is reused at a later date when another export cipher is bound to an SSL or TCP-based SSL virtual server or service. The eRSA key is deleted when the appliance restarts.This parameter is not applicable when configuring a backend profile.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>sessReuse</b>
State of session reuse. Establishing the initial handshake requires CPU-intensive public key encryption operations. With the ENABLED setting, session key exchange is avoided for session resumption requests received from the client.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>cipherRedirect</b>
State of Cipher Redirect. If this parameter is set to ENABLED, you can configure an SSL virtual server or service to display meaningful error messages if the SSL handshake fails because of a cipher mismatch between the virtual server or service and the client.This parameter is not applicable when configuring a backend profile.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>clientAuth</b>
State of client authentication. In service-based SSL offload, the service terminates the SSL handshake if the SSL client does not provide a valid certificate. 
This parameter is not applicable when configuring a backend profile.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>sslRedirect</b>
State of HTTPS redirects for the SSL service. 
For an SSL session, if the client browser receives a redirect message, the browser tries to connect to the new location. However, the secure SSL session breaks if the object has moved from a secure site (https://) to an unsecure site (http://). Typically, a warning message appears on the screen, prompting the user to continue or disconnect.
If SSL Redirect is ENABLED, the redirect message is automatically converted from http:// to https:// and the SSL session does not break.
This parameter is not applicable when configuring a backend profile.
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
State of server authentication support for the SSL Backend profile.
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

<b>clearTextPort</b>
The clearTextPort settings.

<b>insertionEncoding</b>
Encoding method used to insert the subject or issuer's name in HTTP requests to servers.
Possible values: Unicode, UTF-8
Default value: UNICODE_INSERTION

<b>denySSLReneg</b>
Deny renegotiation in specified circumstances. Available settings function as follows:
* NO - Allow SSL renegotiation.
* FRONTEND_CLIENT - Deny secure and nonsecure SSL renegotiation initiated by the client.
* FRONTEND_CLIENTSERVER - Deny secure and nonsecure SSL renegotiation initiated by the client or the NetScaler during policy-based client authentication. 
* ALL - Deny all secure and nonsecure SSL renegotiation.
* NONSECURE - Deny nonsecure SSL renegotiation. Allows only clients that support RFC 5746.
Possible values: NO, FRONTEND_CLIENT, FRONTEND_CLIENTSERVER, ALL, NONSECURE
Default value: NORENEG_FE_BE

<b>quantumSize</b>
Amount of data to collect before the data is pushed to the crypto hardware for encryption. For large downloads, a larger quantum size better utilizes the crypto resources.
Possible values: 4096, 8192, 16384
Default value: 8192

<b>strictCAChecks</b>
Enable strict CA certificate checks on the appliance.
Possible values: YES, NO
Default value: NO

<b>encryptTriggerPktCount</b>
Maximum number of queued packets after which encryption is triggered. Use this setting for SSL transactions that send small packets from server to NetScaler.
Default value: 45
Minimum value: 10
Maximum value: 50

<b>pushFlag</b>
Insert PUSH flag into decrypted, encrypted, or all records. If the PUSH flag is set to a value other than 0, the buffered records are forwarded on the basis of the value of the PUSH flag. Available settings function as follows:
0 - Auto (PUSH flag is not set.)
1 - Insert PUSH flag into every decrypted record.
2 -Insert PUSH flag into every encrypted record.
3 - Insert PUSH flag into every decrypted and encrypted record.
Maximum value: 3

<b>dropReqWithNoHostHeader</b>
Host header check for SNI enabled sessions. If this check is enabled and the HTTP request does not contain the host header for SNI enabled sessions, the request is dropped.
Possible values: YES, NO
Default value: NO

<b>pushEncTriggerTimeout</b>
PUSH encryption trigger timeout value. The timeout value is applied only if you set the Push Encryption Trigger parameter to Timer in the SSL virtual server settings.
Default value: 1
Minimum value: 1
Maximum value: 200

<b>sslTriggerTimeout</b>
Time, in milliseconds, after which encryption is triggered for transactions that are not tracked on the NetScaler appliance because their length is not known. There can be a delay of up to 10ms from the specified timeout value before the packet is pushed into the queue.
Default value: 100
Minimum value: 1
Maximum value: 200



##Example

set ssl profile &lt;profile name&gt; -tls1 ENABLED

##unset ssl profile

Use this command to remove ssl profile settings.Refer to the set ssl profile command for meanings of the arguments.


##Synopsys

unset ssl profile &lt;name> [-dh] [-dhFile] [-dhCount] [-eRSA] [-eRSACount] [-sessReuse] [-sessTimeout] [-cipherRedirect] [-cipherURL] [-clientAuth] [-clientCert] [-sslRedirect] [-redirectPortRewrite] [-nonFipsCiphers] [-ssl3] [-tls1] [-tls11] [-tls12] [-SNIEnable] [-serverAuth] [-commonName] [-pushEncTrigger] [-sendCloseNotify] [-clearTextPort] [-insertionEncoding] [-denySSLReneg] [-quantumSize] [-strictCAChecks] [-encryptTriggerPktCount] [-pushFlag] [-dropReqWithNoHostHeader] [-pushEncTriggerTimeout] [-sslTriggerTimeout]


##show ssl profile

Display all the configured SSL profiles in the system. If a name is specified, then only that profile is shown.


##Synopsys

show ssl profile [&lt;name>]


##Arguments

<b>name</b>
Name of the SSL profile for which to show detailed information.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>dh</b>
State of Diffie-Hellman (DH) key exchange. This parameter is not applicable when configuring a backend profile.

<b>dhFile</b>
Name for and, optionally, path to the PEM-format DH parameter file to be installed. /nsconfig/ssl/ is the default path. This parameter is not applicable when configuring a backend profile.

<b>dhCount</b>
Number of interactions, between the client and the NetScaler appliance, after which the DH private-public pair is regenerated. A value of zero (0) specifies infinite use (no refresh). This parameter is not applicable when configuring a backend profile.

<b>eRSA</b>
State of Ephemeral RSA (eRSA) key exchange. Ephemeral RSA allows clients that support only export ciphers to communicate with the secure server even if the server certificate does not support export clients. The ephemeral RSA key is automatically generated when you bind an export cipher to an SSL or TCP-based SSL virtual server or service. When you remove the export cipher, the eRSA key is not deleted. It is reused at a later date when another export cipher is bound to an SSL or TCP-based SSL virtual server or service. The eRSA key is deleted when the appliance restarts.This parameter is not applicable when configuring a backend profile.

<b>eRSACount</b>
Refresh count for regeneration of RSA public-key and private-key pair. Zero (0) specifies infinite usage (no refresh).This parameter is not applicable when configuring a backend profile.

<b>sessReuse</b>
State of session reuse. Establishing the initial handshake requires CPU-intensive public key encryption operations. With the ENABLED setting, session key exchange is avoided for session resumption requests received from the client.

<b>sessTimeout</b>
Time, in seconds, for which to keep the session active. Any session resumption request receivedafter the timeout period will require a fresh SSL handshake and establishment of a new SSL session.

<b>cipherRedirect</b>
State of Cipher Redirect. If this parameter is set to ENABLED, you can configure an SSL virtual server or service to display meaningful error messages if the SSL handshake fails because of a cipher mismatch between the virtual server or service and the client.This parameter is not applicable when configuring a backend profile.

<b>cipherURL</b>
URL of the page to which to redirect the client in case of a cipher mismatch. Typically, this page has a clear explanation of the error or an alternative location that the transaction can continue from.This parameter is not applicable when configuring a backend profile.

<b>clientAuth</b>
State of client authentication. In service-based SSL offload, the service terminates the SSL handshake if the SSL client does not provide a valid certificate. 
This parameter is not applicable when configuring a backend profile.

<b>clientCert</b>
Type of client authentication. If this parameter is set to MANDATORY, the appliance terminates the SSL handshake if the SSL client does not provide a valid certificate. With the OPTIONAL setting, the appliance requests a certificate from the SSL clients but proceeds with the SSL transaction even if the client presents an invalid certificate.
This parameter is not applicable when configuring a backend SSL profile.
Caution: Define proper access control policies before changing this setting to Optional.

<b>sslRedirect</b>
State of HTTPS redirects for the SSL service. 
For an SSL session, if the client browser receives a redirect message, the browser tries to connect to the new location. However, the secure SSL session breaks if the object has moved from a secure site (https://) to an unsecure site (http://). Typically, a warning message appears on the screen, prompting the user to continue or disconnect.
If SSL Redirect is ENABLED, the redirect message is automatically converted from http:// to https:// and the SSL session does not break.
This parameter is not applicable when configuring a backend profile.

<b>redirectPortRewrite</b>
State of the port rewrite while performing HTTPS redirect. If this parameter is set to ENABLED, and the URL from the server does not contain the standard port, the port is rewritten to the standard.

<b>nonFipsCiphers</b>
State of usage of ciphers that are not FIPS approved. Valid only for an SSL service bound with a FIPS key and certificate.

<b>ssl3</b>
State of SSLv3 protocol support for the SSL service.

<b>tls1</b>
State of TLSv1.0 protocol support for the SSL service.

<b>tls11</b>
State of TLSv1.1 protocol support for the SSL service.Enabled for Front-end service on MPX-CVM platform only.

<b>tls12</b>
State of TLSv1.2 protocol support for the SSL service.Enabled for Front-end service on MPX-CVM platform only.

<b>SNIEnable</b>
State of the Server Name Indication (SNI) feature on the virtual server and service-based offload. SNI helps to enable SSL encryption on multiple domains on a single virtual server or service if the domains are controlled by the same organization and share the same second-level domain name. For example, *.sports.net can be used to secure domains such as login.sports.net and help.sports.net.

<b>serverAuth</b>
State of server authentication support for the SSL Backend profile.

<b>commonName</b>
Name to be checked against the CommonName (CN) field in the server certificate bound to the SSL server

<b>pushEncTrigger</b>
Trigger encryption on the basis of the PUSH flag value. Available settings function as follows:
* ALWAYS - Any PUSH packet triggers encryption.
* IGNORE - Ignore PUSH packet for triggering encryption.
* MERGE - For a consecutive sequence of PUSH packets, the last PUSH packet triggers encryption.
* TIMER - PUSH packet triggering encryption is delayed by the time defined in the set ssl parameter command or in the Change Advanced SSL Settings dialog box.

<b>sendCloseNotify</b>
Enable sending SSL Close-Notify at the end of a transaction

<b>clearTextPort</b>
The clearTextPort settings.

<b>insertionEncoding</b>
Encoding method used to insert the subject or issuer's name in HTTP requests to servers.

<b>denySSLReneg</b>
Deny renegotiation in specified circumstances. Available settings function as follows:
* NO - Allow SSL renegotiation.
* FRONTEND_CLIENT - Deny secure and nonsecure SSL renegotiation initiated by the client.
* FRONTEND_CLIENTSERVER - Deny secure and nonsecure SSL renegotiation initiated by the client or the NetScaler during policy-based client authentication. 
* ALL - Deny all secure and nonsecure SSL renegotiation.
* NONSECURE - Deny nonsecure SSL renegotiation. Allows only clients that support RFC 5746.

<b>quantumSize</b>
Amount of data to collect before the data is pushed to the crypto hardware for encryption. For large downloads, a larger quantum size better utilizes the crypto resources.

<b>strictCAChecks</b>
Enable strict CA certificate checks on the appliance.

<b>encryptTriggerPktCount</b>
Maximum number of queued packets after which encryption is triggered. Use this setting for SSL transactions that send small packets from server to NetScaler.

<b>pushFlag</b>
Insert PUSH flag into decrypted, encrypted, or all records. If the PUSH flag is set to a value other than 0, the buffered records are forwarded on the basis of the value of the PUSH flag. Available settings function as follows:
0 - Auto (PUSH flag is not set.)
1 - Insert PUSH flag into every decrypted record.
2 -Insert PUSH flag into every encrypted record.
3 - Insert PUSH flag into every decrypted and encrypted record.

<b>dropReqWithNoHostHeader</b>
Host header check for SNI enabled sessions. If this check is enabled and the HTTP request does not contain the host header for SNI enabled sessions, the request is dropped.

<b>pushEncTriggerTimeout</b>
PUSH encryption trigger timeout value. The timeout value is applied only if you set the Push Encryption Trigger parameter to Timer in the SSL virtual server settings.

<b>sslTriggerTimeout</b>
Time, in milliseconds, after which encryption is triggered for transactions that are not tracked on the NetScaler appliance because their length is not known. There can be a delay of up to 10ms from the specified timeout value before the packet is pushed into the queue.

<b>sslProfileType</b>
Type of SSL profile.FrontEnd is for front end SSL service or vserver.BackEnd is for backend SSL service.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show ssl profile [profile name]

