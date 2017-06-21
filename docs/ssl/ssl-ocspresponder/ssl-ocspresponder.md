#ssl ocspResponder

The following operations can be performed on "ssl ocspResponder":


[add](#add-ssl-ocspresponder) | [rm](#rm-ssl-ocspresponder) | [set](#set-ssl-ocspresponder) | [unset](#unset-ssl-ocspresponder) | [show](#show-ssl-ocspresponder)

##add ssl ocspResponder

Adds an OCSP responder. An OCSP responder identifies the OCSP server that validates a certificate. NetScaler appliances support OCSP as defined in RFC 2560.


##Synopsys

add ssl ocspResponder &lt;name> -url &lt;URL> [-cache ( ENABLED | DISABLED )  [-cacheTimeout &lt;positive_integer>]] [-batchingDepth &lt;positive_integer>] [-batchingDelay &lt;positive_integer>] [-resptimeout &lt;positive_integer>] [-responderCert &lt;string> | -trustResponder] [-producedAtTimeSkew &lt;positive_integer>] [-signingCert &lt;string>] [-useNonce ( YES | NO )] [-insertClientCert ( YES | NO )]


##Arguments

<b>name</b>
Name for the OCSP responder. Cannot begin with a hash (#) or space character and must contain only ASCII alphanumeric, underscore (_), hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the responder is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my responder" or 'my responder').

<b>url</b>
URL of the OCSP responder.

<b>cache</b>
Enable caching of responses. Caching of responses received from the OCSP responder enables faster responses to the clients and reduces the load on the OCSP responder.
Possible values: ENABLED, DISABLED

<b>cacheTimeout</b>
Timeout for caching the OCSP response. After the timeout, the NetScaler sends a fresh request to the OCSP responder for the certificate status. If a timeout is not specified, the timeout provided in the OCSP response applies.
Default value: 1
Minimum value: 1
Maximum value: 1440

<b>batchingDepth</b>
Number of client certificates to batch together into one OCSP request. Batching avoids overloading the OCSP responder. A value of 1 signifies that each request is queried independently. For a value greater than 1, specify a timeout (batching delay) to avoid inordinately delaying the processing of a single certificate.
Minimum value: 1
Maximum value: 8

<b>batchingDelay</b>
Maximum time, in milliseconds, to wait to accumulate OCSP requests to batch.  Does not apply if the Batching Depth is 1.
Minimum value: 0
Maximum value: 10000

<b>resptimeout</b>
Time, in milliseconds, to wait for an OCSP response. When this time elapses, an error message appears or the transaction is forwarded, depending on the settings on the virtual server. Includes Batching Delay time.
Minimum value: 0
Maximum value: 120000

<b>responderCert</b>

<b>trustResponder</b>
A certificate to use to validate OCSP responses.  Alternatively, if -trustResponder is specified, no verification will be done on the reponse.  If both are omitted, only the response times (producedAt, lastUpdate, nextUpdate) will be verified.

<b>producedAtTimeSkew</b>
Time, in seconds, for which the NetScaler waits before considering the response as invalid. The response is considered invalid if the Produced At time stamp in the OCSP response exceeds or precedes the current NetScaler clock time by the amount of time specified.
Default value: 300
Minimum value: 0
Maximum value: 86400

<b>signingCert</b>
Certificate-key pair that is used to sign OCSP requests. If this parameter is not set, the requests are not signed.

<b>useNonce</b>
Enable the OCSP nonce extension, which is designed to prevent replay attacks.
Possible values: YES, NO

<b>insertClientCert</b>
Include the complete client certificate in the OCSP request.
Possible values: YES, NO



##Example

1) add ssl ocspResponder -url http://ocsp.example.com -producedAtTimeSkew 0The above command will only allow responses that were generated in the same second to be used.  That is, if the response was generated at 12:00:01, it would have to be received by the NetScaler by 12:00:59 to be considered still valid.2) add ssl ocspResponder -url http://ocsp.example.com -producedAtTimeSkew 300This command will allow responses to vary up to five minutes plus or minus.  That is, if the response has a producedAt time of 12:00:00, it will be accepted at the NetScaler if the local clock is between 11:55:00 and 12:05:00

##rm ssl ocspResponder

Removes the specified OCSP responder from the appliance.


##Synopsys

rm ssl ocspResponder &lt;name> ...


##Arguments

<b>name</b>
Name of the OCSP responder to remove. The OCSP responder is removed only if it is not referenced by any other object.



##Example

1)	rm ssl ocspResponder o1The above command removes the OCSP responder o1 from the system.

##set ssl ocspResponder

Modifies the parameters of an OCSP responder.


##Synopsys

set ssl ocspResponder &lt;name> [-url &lt;URL>] [-cache ( ENABLED | DISABLED )] [-cacheTimeout &lt;positive_integer>] [-batchingDepth &lt;positive_integer>] [-batchingDelay &lt;positive_integer>] [-resptimeout &lt;positive_integer>] [-responderCert &lt;string> | -trustResponder] [-producedAtTimeSkew &lt;positive_integer>] [-signingCert &lt;string>] [-useNonce ( YES | NO )] [-insertClientCert ( YES | NO )]


##Arguments

<b>name</b>
Name of the OCSP responder to modify.

<b>url</b>
URL of the OCSP responder.

<b>cache</b>
Enable caching of responses. Caching of responses received from the OCSP responder enables faster responses to the clients and reduces the load on the OCSP responder.
Possible values: ENABLED, DISABLED

<b>cacheTimeout</b>
Timeout for caching the OCSP response. After the timeout, the NetScaler sends a fresh request to the OCSP responder for the certificate status. If a timeout is not specified, the timeout provided in the OCSP response applies.
Default value: 1
Minimum value: 1
Maximum value: 1440

<b>batchingDepth</b>
Number of client certificates to batch together into one OCSP request. Batching avoids overloading the OCSP responder. A value of 1 signifies that each request is queried independently. For a value greater than 1, specify a timeout (batching delay) to avoid inordinately delaying the processing of a single certificate.
Minimum value: 1
Maximum value: 8

<b>batchingDelay</b>
Maximum time, in milliseconds, to wait to accumulate OCSP requests to batch.  Does not apply if the Batching Depth is 1.
Minimum value: 0
Maximum value: 10000

<b>resptimeout</b>
Time, in milliseconds, to wait for an OCSP response. When this time elapses, an error message appears or the transaction is forwarded, depending on the settings on the virtual server. Includes Batching Delay time.
Minimum value: 0
Maximum value: 120000

<b>responderCert</b>

<b>trustResponder</b>
A certificate to use to validate OCSP responses.  Alternatively, if -trustResponder is specified, no verification will be done on the reponse.  If both are omitted, only the response times (producedAt, lastUpdate, nextUpdate) will be verified.

<b>producedAtTimeSkew</b>
Time, in seconds, for which the NetScaler waits before considering the response as invalid. The response is considered invalid if the Produced At time stamp in the OCSP response exceeds or precedes the current NetScaler clock time by the amount of time specified.
Default value: 300
Minimum value: 0
Maximum value: 86400

<b>signingCert</b>
Certificate-key pair that is used to sign OCSP requests. If this parameter is not set, the requests are not signed.

<b>useNonce</b>
Enable the OCSP nonce extension, which is designed to prevent replay attacks.
Possible values: YES, NO

<b>insertClientCert</b>
Include the complete client certificate in the OCSP request.
Possible values: YES, NO



##Example

1) add ssl ocspResponder -url http://ocsp.example.com -producedAtTimeSkew 0The above command will only allow responses that were generated in the same second to be used.  That is, if the response was generated at 12:00:01, it would have to be received by the NetScaler by 12:00:59 to be considered still valid.2) add ssl ocspResponder -url http://ocsp.example.com -producedAtTimeSkew 300This command will allow responses to vary up to five minutes plus or minus.  That is, if the response has a producedAt time of 12:00:00, it will be accepted at the NetScaler if the local clock is between 11:55:00 and 12:05:00

##unset ssl ocspResponder

Removes the attributes of an OCSP responder. Attributes for which a default value is available revert to their default values. Refer to the set ssl ocspResponder command for descriptions of the arguments..Refer to the set ssl ocspResponder command for meanings of the arguments.


##Synopsys

unset ssl ocspResponder &lt;name> [-trustResponder] [-insertClientCert ( YES | NO )] [-cache] [-cacheTimeout] [-batchingDepth] [-batchingDelay] [-resptimeout] [-responderCert] [-producedAtTimeSkew] [-signingCert] [-useNonce]


##show ssl ocspResponder

Displays information about all the OCSP responders configured on the appliance, or displays detailed information about the specified OCSP responder.


##Synopsys

show ssl ocspResponder [&lt;name>]


##Arguments

<b>name</b>
Name of the OCSP responder for which to show detailed information.



##Outputs

<b>url</b>
URL of the OCSP responder.

<b>useAIA</b>
Only use the URL present in the certificate.

<b>cache</b>
Enable caching of responses. Caching of responses received from the OCSP responder enables faster responses to the clients and reduces the load on the OCSP responder.

<b>cacheTimeout</b>
Timeout for caching the OCSP response. After the timeout, the NetScaler sends a fresh request to the OCSP responder for the certificate status. If a timeout is not specified, the timeout provided in the OCSP response applies.

<b>batchingDepth</b>
Number of client certificates to batch together into one OCSP request. Batching avoids overloading the OCSP responder. A value of 1 signifies that each request is queried independently. For a value greater than 1, specify a timeout (batching delay) to avoid inordinately delaying the processing of a single certificate.

<b>batchingDelay</b>
Maximum time, in milliseconds, to wait to accumulate OCSP requests to batch.  Does not apply if the Batching Depth is 1.

<b>resptimeout</b>
Maximum time, in mS, to wait for an OCSP response before giving up.  Defaults to 2000 mS.  If this is set to 0, NetScaler will wait for an indefinite amount of time.

<b>producedAtTimeSkew</b>
Time, in seconds, for which the NetScaler waits before considering the response as invalid. The response is considered invalid if the Produced At time stamp in the OCSP response exceeds or precedes the current NetScaler clock time by the amount of time specified.

<b>responderCert</b>

<b>trustResponder</b>
A certificate to use to validate OCSP responses.  Alternatively, if -trustResponder is specified, no verification will be done on the reponse.  If both are omitted, only the response times (producedAt, lastUpdate, nextUpdate) will be verified.

<b>signingCert</b>
Certificate-key pair that is used to sign OCSP requests. If this parameter is not set, the requests are not signed.

<b>useNonce</b>
Add a nonce to the OCSP request.  Protects against replay attacks.

<b>dns</b>
Was DNS resolution successful for a domain-based OCSP responder

<b>insertClientCert</b>
Include the complete client certificate in the OCSP request.

<b>IPAddress</b>
The IPv6 address of the ocsp responder.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



