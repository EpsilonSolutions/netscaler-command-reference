#ssl action

The following operations can be performed on "ssl action":


[add](#add-ssl-action) | [rm](#rm-ssl-action) | [show](#show-ssl-action)

##add ssl action

Creates a new SSL action. An SSL action defines SSL settings that you can apply to the selected requests. You associate an action with one or more policies. Data in client connection requests or responses is compared to a rule (expression) specified in the policy, and the action is applied to connections that match the rule.


##Synopsys

add ssl action &lt;name> [-clientAuth ( DOCLIENTAUTH | NOCLIENTAUTH )] [-clientCert ( ENABLED | DISABLED )  -certHeader &lt;string>] [-clientCertSerialNumber ( ENABLED | DISABLED )  -certSerialHeader &lt;string>] [-clientCertSubject ( ENABLED | DISABLED )  -certSubjectHeader &lt;string>] [-clientCertHash ( ENABLED | DISABLED )  -certHashHeader &lt;string>] [-clientCertIssuer ( ENABLED | DISABLED )  -certIssuerHeader &lt;string>] [-sessionID ( ENABLED | DISABLED )  -sessionIDHeader &lt;string>] [-cipher ( ENABLED | DISABLED )  -cipherHeader &lt;string>] [-clientCertNotBefore ( ENABLED | DISABLED )  -certNotBeforeHeader &lt;string>] [-clientCertNotAfter ( ENABLED | DISABLED )  -certNotAfterHeader &lt;string>] [-OWASupport ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name for the SSL action. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').

<b>clientAuth</b>
Perform client certificate authentication.
Possible values: DOCLIENTAUTH, NOCLIENTAUTH

<b>clientCert</b>
Insert the entire client certificate into the HTTP header of the request being sent to the web server. The certificate is inserted in ASCII (PEM) format.
Possible values: ENABLED, DISABLED

<b>certHeader</b>
Name of the header into which to insert the client certificate.

<b>clientCertSerialNumber</b>
Insert the entire client serial number into the HTTP header of the request being sent to the web server.
Possible values: ENABLED, DISABLED

<b>certSerialHeader</b>
Name of the header into which to insert the client serial number.

<b>clientCertSubject</b>
Insert the client certificate subject, also known as the distinguished name (DN), into the HTTP header of the request being sent to the web server.
Possible values: ENABLED, DISABLED

<b>certSubjectHeader</b>
Name of the header into which to insert the client certificate subject.

<b>clientCertHash</b>
Insert the certificate signature (hash) into the HTTP header of the request being sent to the web server.
Possible values: ENABLED, DISABLED

<b>certHashHeader</b>
Name of the header into which to insert the client certificate signature (hash).

<b>clientCertIssuer</b>
Insert the certificate issuer details into the HTTP header of the request being sent to the web server.
Possible values: ENABLED, DISABLED

<b>certIssuerHeader</b>
Name of the header into which to insert the client certificate issuer details.

<b>sessionID</b>
Insert the SSL session ID into the HTTP header of the request being sent to the web server. Every SSL connection that the client and the NetScaler share has a unique ID that identifies the specific connection.
Possible values: ENABLED, DISABLED

<b>sessionIDHeader</b>
Name of the header into which to insert the Session ID.

<b>cipher</b>
Insert the cipher suite that the client and the NetScaler appliance negotiated for the SSL session into the HTTP header of the request being sent to the web server. The appliance inserts the cipher-suite name, SSL protocol, export or non-export string, and cipher strength bit, depending on the type of browser connecting to the SSL virtual server or service (for example, Cipher-Suite: RC4- MD5 SSLv3 Non-Export 128-bit).
Possible values: ENABLED, DISABLED

<b>cipherHeader</b>
Name of the header into which to insert the name of the cipher suite.

<b>clientCertNotBefore</b>
Insert the date from which the certificate is valid into the HTTP header of the request being sent to the web server. Every certificate is configured with the date and time from which it is valid.
Possible values: ENABLED, DISABLED

<b>certNotBeforeHeader</b>
Name of the header into which to insert the date and time from which the certificate is valid.

<b>clientCertNotAfter</b>
Insert the date of expiry of the certificate into the HTTP header of the request being sent to the web server. Every certificate is configured with the date and time at which the certificate expires.
Possible values: ENABLED, DISABLED

<b>certNotAfterHeader</b>
Name of the header into which to insert the certificate's expiry date.

<b>OWASupport</b>
If the appliance is in front of an Outlook Web Access (OWA) server, insert a special header field, FRONT-END-HTTPS: ON, into the HTTP requests going to the OWA server. This header communicates to the server that the transaction is HTTPS and not HTTP.
Possible values: ENABLED, DISABLED



##Example

add ssl action certInsert_act -clientCert ENABLED -certHeader CERT

##rm ssl action

Removes the specified SSL action.


##Synopsys

rm ssl action &lt;name>


##Arguments

<b>name</b>
Name of the SSL action to remove.



##Example

rm ssl action certInsert_act

##show ssl action

Displays information about all the SSL actions configured on the appliance, or displays detailed information about the specified SSL action.


##Synopsys

show ssl action [&lt;name>]


##Arguments

<b>name</b>
Name of the SSL action for which to show detailed information.



##Outputs

<b>stateflag</b>

<b>clientAuth</b>
Perform client certificate authentication.

<b>clientCert</b>
Insert the entire client certificate into the HTTP header of the request being sent to the web server. The certificate is inserted in ASCII (PEM) format.

<b>certHeader</b>

<b>clientCertSerialNumber</b>
Insert the entire client serial number into the HTTP header of the request being sent to the web server.

<b>certSerialHeader</b>

<b>clientCertSubject</b>
Insert the client certificate subject, also known as the distinguished name (DN), into the HTTP header of the request being sent to the web server.

<b>certSubjectHeader</b>

<b>clientCertHash</b>
Insert the certificate signature (hash) into the HTTP header of the request being sent to the web server.

<b>certHashHeader</b>

<b>clientCertIssuer</b>
Insert the certificate issuer details into the HTTP header of the request being sent to the web server.

<b>certIssuerHeader</b>

<b>sessionID</b>
Insert the SSL session ID into the HTTP header of the request being sent to the web server. Every SSL connection that the client and the NetScaler share has a unique ID that identifies the specific connection.

<b>sessionIDHeader</b>

<b>cipher</b>
Insert the cipher suite that the client and the NetScaler appliance negotiated for the SSL session into the HTTP header of the request being sent to the web server. The appliance inserts the cipher-suite name, SSL protocol, export or non-export string, and cipher strength bit, depending on the type of browser connecting to the SSL virtual server or service (for example, Cipher-Suite: RC4- MD5 SSLv3 Non-Export 128-bit).

<b>cipherHeader</b>

<b>OWASupport</b>
If the appliance is in front of an Outlook Web Access (OWA) server, insert a special header field, FRONT-END-HTTPS: ON, into the HTTP requests going to the OWA server. This header communicates to the server that the transaction is HTTPS and not HTTP.

<b>clientCertNotBefore</b>
Insert the date from which the certificate is valid into the HTTP header of the request being sent to the web server. Every certificate is configured with the date and time from which it is valid.

<b>certNotBeforeHeader</b>

<b>clientCertNotAfter</b>
Insert the date of expiry of the certificate into the HTTP header of the request being sent to the web server. Every certificate is configured with the date and time at which the certificate expires.

<b>certNotAfterHeader</b>

<b>hits</b>
The number of times the action has been taken.

<b>undefHits</b>
The number of times the action resulted in UNDEF.

<b>referenceCount</b>
The number of references to the action.

<b>description</b>
Description of the action

<b>flags</b>

<b>builtin</b>
Flag to determine whether ssl action is built-in or not

<b>devno</b>

<b>count</b>



##Example

show ssl action1 Configured SSL action:1)      Name: certInsert_act        Data Insertion Action:        Cert Header: ENABLED            Cert Tag: CERT

