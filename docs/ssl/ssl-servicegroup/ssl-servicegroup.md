#ssl serviceGroup

The following operations can be performed on "ssl serviceGroup":


[set](#set-ssl-servicegroup) | [unset](#unset-ssl-servicegroup) | [bind](#bind-ssl-servicegroup) | [unbind](#unbind-ssl-servicegroup) | [show](#show-ssl-servicegroup)

##set ssl serviceGroup

Sets the advanced SSL configuration for an SSL service group.


##Synopsys

set ssl serviceGroup &lt;serviceGroupName>@ [-sslProfile &lt;string>] [-sessReuse ( ENABLED | DISABLED )  [-sessTimeout &lt;positive_integer>]] [-nonFipsCiphers ( ENABLED | DISABLED )] [-ssl3 ( ENABLED | DISABLED )] [-tls1 ( ENABLED | DISABLED )] [-serverAuth ( ENABLED | DISABLED )  [-commonName &lt;string>]] [-sendCloseNotify ( YES | NO )]


##Arguments

<b>serviceGroupName</b>
Name of the SSL service group for which to set advanced configuration.

<b>sslProfile</b>
SSL Profile associated to serviceGroup

<b>sessReuse</b>
State of session reuse. Establishing the initial handshake requires CPU-intensive public key encryption operations. With the ENABLED setting, session key exchange is avoided for session resumption requests received from the client.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>nonFipsCiphers</b>
State of usage of ciphers that are not FIPS approved. Valid only for an SSL service bound with a FIPS key and certificate.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>ssl3</b>
State of SSLv3 protocol support for the SSL service group.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>tls1</b>
State of TLSv1.0 protocol support for the SSL service group.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>serverAuth</b>
State of server authentication support for the SSL service group.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>sendCloseNotify</b>
Enable sending SSL Close-Notify at the end of a transaction
Possible values: YES, NO
Default value: YES



##Example

1)	set ssl servicegroup svcg1 -sessReuse DISABLEDThe above example disables session reuse for the service group 'svcg1'.

##unset ssl serviceGroup

Use this command to remove ssl serviceGroup settings.Refer to the set ssl serviceGroup command for meanings of the arguments.


##Synopsys

unset ssl serviceGroup &lt;serviceGroupName>@ [-sslProfile] [-sessReuse] [-sessTimeout] [-nonFipsCiphers] [-ssl3] [-tls1] [-serverAuth] [-commonName] [-sendCloseNotify]


##bind ssl serviceGroup

Bind a SSL certkey or a SSL policy to a SSL service.


##Synopsys

bind ssl serviceGroup &lt;serviceGroupName>@ ((-certkeyName &lt;string>  [(-CA  [-crlCheck ( Mandatory | Optional ) | -ocspCheck ( Mandatory | Optional )]) | -SNICert] ) | -cipherName &lt;string>)


##Arguments

<b>serviceGroupName</b>
The name of the SSL service to which the SSL policy needs to be bound.

<b>certkeyName</b>
The name of the CertKey

<b>cipherName</b>
A cipher-suite can consist of an individual cipher name, the system predefined cipher-alias name, or user defined cipher-group name.



##Example

bind ssl service ssl_svc -policyName certInsert_pol -priority 10

##unbind ssl serviceGroup

Unbind a SSL policy from a SSL service.


##Synopsys

unbind ssl serviceGroup &lt;serviceGroupName>@ ((-certkeyName &lt;string>  [(-CA  [-crlCheck ( Mandatory | Optional )]) | -SNICert] ) | -cipherName &lt;string>)


##Arguments

<b>serviceGroupName</b>
The name of the SSL service from which the SSL policy needs to be unbound.

<b>certkeyName</b>
The name of the certificate bound to the SSL service group.

<b>cipherName</b>
A cipher-suite can consist of an individual cipher name, the system predefined cipher-alias name, or user defined cipher-group name.



##Example

unbind ssl service ssl_svc -policyName certInsert_pol

##show ssl serviceGroup

Displays information about SSL-specific configuration for all SSL service groups, or displays detailed information about the specified SSL service group.


##Synopsys

show ssl serviceGroup [&lt;serviceGroupName>] [-cipherDetails]


##Arguments

<b>serviceGroupName</b>
Name of the SSL service group for which to show detailed information.

<b>cipherDetails</b>
Display details of the individual ciphers bound to the SSL service group.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>dh</b>
The state of DH key exchange support for the SSL service group.

<b>dhFile</b>
The  file name and path for the DH parameter.

<b>dhCount</b>
The  refresh  count  for  the re-generation of DH public-key and private-key from the DH parameter.

<b>eRSA</b>
The state of Ephemeral RSA key exchange support for the SSL service group.Ephemeral RSA is used for export ciphers.

<b>eRSACount</b>
The  refresh  count  for the re-generation of RSA public-key and private-key pair.

<b>sessReuse</b>
The  state of session re-use support for the SSL service group.

<b>sessTimeout</b>
The Session timeout value in seconds.

<b>cipherRedirect</b>
The state of Cipher Redirect feature. Cipher Redirect feature can be used to provide more readable information to SSL clients about mismatch in ciphers between the client and the SSL vserver.

<b>cipherURL</b>
The redirect URL to be used with the  Cipher  Redirect  feature.

<b>sslv2Redirect</b>
The state of SSLv2 Redirect feature.SSLv2 Redirect feature can be used to provide more readable information to SSL client about non-support of SSLv2 protocol on the SSL vserver.

<b>sslv2URL</b>
The  redirect URL to be used with SSLv2 Redirect feature.

<b>clientAuth</b>
The state of Client-Authentication support for the SSL service group.

<b>clientCert</b>
The rule for client certificate requirement in client authentication.

<b>sslRedirect</b>
The state of HTTPS redirects for the SSL service group.
This is required for the proper functioning of the redirect messages from the server. The redirect message from the server provides the new location for the moved object. This is contained in the HTTP header field: Location, e.g. Location: http://www.moved.org/here.html
For the SSL session, if the client browser receives this message, the browser will try to connect to the new location. This will break the secure SSL session, as the object has moved from a secure site (https://) to an un-secure one (http://). Generally browsers flash a warning message on the screen and prompt the user, either to continue or disconnect.
The above feature, when enabled will automatically convert all such http:// redirect message to https://. This will not break the client SSL session.
Note: The set ssl service command can be used for configuring a front-end SSL service for service based SSL Off-Loading, or a backend SSL service for backend-encryption setup.

<b>redirectPortRewrite</b>
The state of port-rewrite feature.

<b>nonFipsCiphers</b>
The state of usage of non FIPS approved ciphers.

<b>ssl2</b>
The  state of SSLv2 protocol support for the SSL service group.

<b>ssl3</b>
State of SSLv3 protocol support for the SSL service group.

<b>tls1</b>
State of TLSv1.0 protocol support for the SSL service group.

<b>serverAuth</b>
The state of the server authentication configuration for the SSL service group. For SSL deployments where data is encrypted end-to-end using SSL, you can authenticate the server.

<b>commonName</b>
Name to be checked against the CommonName (CN) field in the server certificate bound to the SSL server

<b>cipherAliasName/cipherName/cipherGroupName</b>
The name of the cipher group/alias/name configured for the SSL service group.

<b>cipherName</b>
The name of the cipher group/alias/name configured for the SSL service group.

<b>ocspCheck</b>
The state of the OCSP check parameter. (Mandatory/Optional)

<b>crlCheck</b>
The state of the CRL check parameter. (Mandatory/Optional)

<b>description</b>
The description of the cipher.

<b>certkeyName</b>
The name of the certificate bound to the SSL service group.

<b>clearTextPort</b>
The port on the back-end web-servers where the clear-text data is sent by system. Use this setting for the wildcard IP based SSL Acceleration configuration (*:443).

<b>serviceName</b>
The service name.

<b>CA</b>
CA certificate.

<b>SNICert</b>
The name of the CertKey. Use this option to bind Certkey(s) which will be used in SNI processing.

<b>stateflag</b>

<b>sendCloseNotify</b>
Enable sending SSL Close-Notify at the end of a transaction

<b>sslProfile</b>
SSL Profile associated to serviceGroup

<b>devno</b>

<b>count</b>



##Example

An example of output of show ssl servicegroup command is as shown belowshow ssl servicegroup ssl_svcg        Advanced SSL configuration for Back-end SSL Service Group ssl_svcg:        Session Reuse: ENABLED          Timeout: 300 seconds        Server Auth: DISABLED        Non FIPS Ciphers: DISABLED        SSLv3: ENABLED  TLSv1: ENABLED1)      Cipher Name: ALL        Description: Predefined Cipher Alias

