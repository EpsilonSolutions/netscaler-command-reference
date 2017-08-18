#ssl parameter

The following operations can be performed on "ssl parameter":


[set](#set-ssl-parameter) | [unset](#unset-ssl-parameter) | [show](#show-ssl-parameter)

##set ssl parameter




##Synopsys

set ssl parameter [-quantumSize &lt;quantumSize>] [-crlMemorySizeMB &lt;positive_integer>] [-strictCAChecks ( YES | NO )] [-sslTriggerTimeout &lt;positive_integer>] [-sendCloseNotify ( YES | NO )] [-encryptTriggerPktCount &lt;positive_integer>] [-denySSLReneg &lt;denySSLReneg>] [-insertionEncoding ( Unicode | UTF-8 )] [-ocspCacheSize &lt;positive_integer>] [-pushFlag &lt;positive_integer>] [-dropReqWithNoHostHeader ( YES | NO )] [-pushEncTriggerTimeout &lt;positive_integer>] [-cryptodevDisableLimit &lt;positive_integer>] [-undefActionControl &lt;string>] [-undefActionData &lt;string>] [-defaultProfile ( ENABLED | DISABLED )] [-softwareCryptoThreshold &lt;positive_integer>] [-hybridFIPSMode ( ENABLED | DISABLED )] [-sigDigestType &lt;sigDigestType> ...] [-ssliErrorCache ( ENABLED | DISABLED )] [-ssliMaxErrorCacheMem &lt;positive_integer>] [-insertCertSpace ( YES | NO )]


##Arguments

<b>quantumSize</b>
Amount of data to collect before the data is pushed to the crypto hardware for encryption. For large downloads, a larger quantum size better utilizes the crypto resources.
Possible values: 4096, 8192, 16384
Default value: 8192

<b>crlMemorySizeMB</b>
Maximum memory size to use for certificate revocation lists (CRLs). This parameter reserves memory for a CRL but sets a limit to the maximum memory that the CRLs loaded on the appliance can consume.
Default value: 256
Minimum value: 10
Maximum value: 1024

<b>strictCAChecks</b>
Enable strict CA certificate checks on the appliance.
Possible values: YES, NO
Default value: NO

<b>sslTriggerTimeout</b>
Time, in milliseconds, after which encryption is triggered for transactions that are not tracked on the NetScaler appliance because their length is not known. There can be a delay of up to 10ms from the specified timeout value before the packet is pushed into the queue.
Default value: 100
Minimum value: 1
Maximum value: 200

<b>sendCloseNotify</b>
Send an SSL Close-Notify message to the client at the end of a transaction.
Possible values: YES, NO
Default value: YES

<b>encryptTriggerPktCount</b>
Maximum number of queued packets after which encryption is triggered. Use this setting for SSL transactions that send small packets from server to NetScaler.
Default value: 45
Minimum value: 10
Maximum value: 50

<b>denySSLReneg</b>
Deny renegotiation in specified circumstances. Available settings function as follows:
* NO - Allow SSL renegotiation.
* FRONTEND_CLIENT - Deny secure and nonsecure SSL renegotiation initiated by the client.
* FRONTEND_CLIENTSERVER - Deny secure and nonsecure SSL renegotiation initiated by the client or the NetScaler during policy-based client authentication. 
* ALL - Deny all secure and nonsecure SSL renegotiation.
* NONSECURE - Deny nonsecure SSL renegotiation. Allows only clients that support RFC 5746.
Possible values: NO, FRONTEND_CLIENT, FRONTEND_CLIENTSERVER, ALL, NONSECURE
Default value: ALL

<b>insertionEncoding</b>
Encoding method used to insert the subject or issuer's name in HTTP requests to servers.
Possible values: Unicode, UTF-8
Default value: Unicode

<b>ocspCacheSize</b>
Size, per packet engine, in megabytes, of the OCSP cache. A maximum of 10% of the packet engine memory can be assigned. Because the maximum allowed packet engine memory is 4GB, the maximum value that can be assigned to the OCSP cache is approximately 410 MB.
Default value: 10
Minimum value: 0
Maximum value: 512

<b>pushFlag</b>
Insert PUSH flag into decrypted, encrypted, or all records. If the PUSH flag is set to a value other than 0, the buffered records are forwarded on the basis of the value of the PUSH flag. Available settings function as follows:
0 - Auto (PUSH flag is not set.)
1 - Insert PUSH flag into every decrypted record.
2 -Insert PUSH flag into every encrypted record.
3 - Insert PUSH flag into every decrypted and encrypted record.
Minimum value: 0
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

<b>cryptodevDisableLimit</b>
Limit to the number of disabled SSL chips after which the ADC restarts. A value of zero implies that the ADC does not automatically restart.
Default value: 0
Minimum value: 0

<b>undefActionControl</b>
Name of the undefined built-in control action: CLIENTAUTH, NOCLIENTAUTH, NOOP, RESET, or DROP.
Default value: "CLIENTAUTH"

<b>undefActionData</b>
Name of the undefined built-in data action: NOOP, RESET or DROP.
Default value: "NOOP"

<b>defaultProfile</b>
Global parameter used to enable default profile feature.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>softwareCryptoThreshold</b>
Netscaler CPU utilization threshold (in percentage) beyond which crypto operations are not done in software.
A value of zero implies that CPU is not utilized for doing crypto in software.
Default value: 0
Minimum value: 0
Maximum value: 100

<b>hybridFIPSMode</b>
When this mode is enabled, system will use additional crypto hardware to accelerate symmetric crypto operations.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>sigDigestType</b>
Signature Digest Algorithms that are supported by appliance. Default value is "ALL" and it will enable the following algorithms depending on the platform.
On VPX: RSA-MD5 RSA-SHA1 RSA-SHA224 RSA-SHA256 RSA-SHA384 RSA-SHA512 DSA-SHA1 DSA-SHA224 DSA-SHA256 DSA-SHA384 DSA-SHA512
On MPX with Nitrox-III Cards: RSA-MD5 RSA-SHA1 RSA-SHA224 RSA-SHA256 RSA-SHA384 RSA-SHA512 ECDSA-SHA1 ECDSA-SHA224 ECDSA-SHA256 ECDSA-SHA384 ECDSA-SHA512
Others: RSA-MD5 RSA-SHA1 RSA-SHA224 RSA-SHA256 RSA-SHA384 RSA-SHA512.
Default value: ALL

<b>ssliErrorCache</b>
Enable or disable dynamically learning and caching the learned information to make the subsequent interception or bypass decision. When enabled, NS does the lookup of this cached data to do early bypass.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>ssliMaxErrorCacheMem</b>
Specify the maximum memory that can be used for caching the learned data. This memory is used as a LRU cache so that the old entries gets replaced with new entry once the set memory limit is fully utilised. A value of 0 decides the limit automatically.
Default value: 0
Minimum value: 0
Maximum value: 4294967294

<b>insertCertSpace</b>
To insert space between lines in the certificate header of request
Possible values: YES, NO
Default value: YES



##unset ssl parameter

Use this command to remove ssl parameter settings.Refer to the set ssl parameter command for meanings of the arguments.


##Synopsys

unset ssl parameter [-quantumSize] [-crlMemorySizeMB] [-strictCAChecks] [-sslTriggerTimeout] [-sendCloseNotify] [-encryptTriggerPktCount] [-denySSLReneg] [-insertionEncoding] [-ocspCacheSize] [-pushFlag] [-dropReqWithNoHostHeader] [-pushEncTriggerTimeout] [-cryptodevDisableLimit] [-undefActionControl] [-undefActionData] [-defaultProfile] [-softwareCryptoThreshold] [-hybridFIPSMode] [-sigDigestType] [-ssliErrorCache] [-ssliMaxErrorCacheMem] [-insertCertSpace]


##show ssl parameter

Displays information about advanced SSL parameters.


##Synopsys

show ssl parameter


##Outputs

<b>quantumSize</b>
Amount of data to collect before the data is pushed to the crypto hardware for encryption. For large downloads, a larger quantum size better utilizes the crypto resources.

<b>crlMemorySizeMB</b>
Maximum memory size to use for certificate revocation lists (CRLs). This parameter reserves memory for a CRL but sets a limit to the maximum memory that the CRLs loaded on the appliance can consume.

<b>strictCAChecks</b>
Memory size to use for CRLs

<b>sslTriggerTimeout</b>
Encryption trigger timer. Set the encryption trigger timeout for transactions, which are not trackable by Netscaler. NetScaler will use this setting to accumulate data received from the server for the configured time period before pushing it to the crypto hardware for encryption.

<b>sendCloseNotify</b>
Send an SSL Close-Notify message to the client at the end of a transaction.

<b>encryptTriggerPktCount</b>
Maximum number of queued packets after which encryption is triggered. Use this setting for SSL transactions that send small packets from server to NetScaler.

<b>denySSLReneg</b>
SSL Renegotiation setting

<b>insertionEncoding</b>
Encoding method used to insert the subject or issuer's name in HTTP requests to servers.

<b>ocspCacheSize</b>
Size, per packet engine, in megabytes of the OCSP cache

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

<b>cryptodevDisableLimit</b>
Limit to the number of disabled SSL chips after which the ADC restarts. A value of zero implies that the ADC does not automatically restart.

<b>undefActionControl</b>
Global undef action for SSL control policies

<b>undefActionData</b>
Global undef action for SSL data policies

<b>defaultProfile</b>
Global parameter used to enable default profile feature.

<b>svctls1112disable</b>
Disable TLS 1.1 and 1.2 for dynamic and VPN created services.

<b>montls1112disable</b>
Disable TLS 1.1 and 1.2 for secure (https) monitors bound to SSL_BRIDGE services.

<b>softwareCryptoThreshold</b>
CPU quota (%) to be allocated for crypto acceleration in software. Once the CPU utilization reaches or crosses this limit, CPU won't be used for driving crypto in software.

<b>hybridFIPSMode</b>
When this mode is enabled, system will use additional crypto hardware to accelerate symmetric crypto operations.

<b>sigDigestType</b>
Signature Digest Algorithms that are supported by appliance. Default value is "ALL" and it will enable the following algorithms depending on the platform.
On VPX: RSA-MD5 RSA-SHA1 RSA-SHA224 RSA-SHA256 RSA-SHA384 RSA-SHA512 DSA-SHA1 DSA-SHA224 DSA-SHA256 DSA-SHA384 DSA-SHA512
On MPX with Nitrox-III Cards: RSA-MD5 RSA-SHA1 RSA-SHA224 RSA-SHA256 RSA-SHA384 RSA-SHA512 ECDSA-SHA1 ECDSA-SHA224 ECDSA-SHA256 ECDSA-SHA384 ECDSA-SHA512
Others: RSA-MD5 RSA-SHA1 RSA-SHA224 RSA-SHA256 RSA-SHA384 RSA-SHA512.

<b>ssliErrorCache</b>
Enable or disable dynamically learning and caching the learned information to make the subsequent interception or bypass decision. When enabled, NS does the lookup of this cached data to do early bypass.

<b>ssliMaxErrorCacheMem</b>
Specify the maximum memory that can be used for caching the learned data. This memory is used as a LRU cache so that the old entries gets replaced with new entry once the set memory limit is fully utilised. A value of 0 decides the limit automatically.

<b>insertCertSpace</b>
To insert space between lines in the certificate header of request



