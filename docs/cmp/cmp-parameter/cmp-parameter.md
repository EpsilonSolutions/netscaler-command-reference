#cmp parameter

The following operations can be performed on "cmp parameter":


[set](#set-cmp-parameter) | [unset](#unset-cmp-parameter) | [show](#show-cmp-parameter)

##set cmp parameter

Configures the compression parameters.


##Synopsys

set cmp parameter [-cmpLevel &lt;cmpLevel>] [-quantumSize &lt;positive_integer>] [-serverCmp ( ON | OFF )] [-minResSize &lt;positive_integer>] [-cmpBypassPct &lt;positive_integer>] [-cmpOnPush ( ENABLED | DISABLED )] [-policyType ( CLASSIC | ADVANCED )] [-addVaryHeader ( ENABLED | DISABLED )  [-varyHeaderValue &lt;string>]] [-externalCache ( YES | NO )]


##Arguments

<b>cmpLevel</b>
Specify a compression level. Available settings function as follows:
 * Optimal - Corresponds to a gzip GZIP level of 5-7.
 * Best speed - Corresponds to a gzip level of 1.
 * Best compression - Corresponds to a gzip level of 9.
Possible values: optimal, bestspeed, bestcompression
Default value: optimal

<b>quantumSize</b>
Minimum quantum of data to be filled before compression begins.
Default value: 57344
Minimum value: 8
Maximum value: 63488

<b>serverCmp</b>
Allow the server to send compressed data to the NetScaler appliance. With the default setting, the NetScaler appliance handles all compression.
Possible values: ON, OFF
Default value: ON

<b>minResSize</b>
Smallest response size, in bytes, to be compressed.
Minimum value: 0

<b>cmpBypassPct</b>
NetScaler CPU threshold after which compression is not performed. Range: 0 - 100
Default value: 100
Minimum value: 0
Maximum value: 100

<b>cmpOnPush</b>
NetScaler appliance does not wait for the quantum to be filled before starting to compress data. Upon receipt of a packet with a PUSH flag, the appliance immediately begins compression of the accumulated packets.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>policyType</b>
Type of policy. Available settings function as follows:
 * Classic -  Classic policies evaluate basic characteristics of traffic and other data.
 * Advanced -  Advanced policies (which have been renamed as default syntax policies) can perform the same type of evaluations as classic policies. They also enable you to analyze more data (for example, the body of an HTTP request) and to configure more operations in the policy rule (for example, transforming data in the body of a request into an HTTP header).
Possible values: CLASSIC, ADVANCED

<b>addVaryHeader</b>
Control insertion of the Vary header in HTTP responses compressed by NetScaler. Intermediate caches store different versions of the response for different values of the headers present in the Vary response header.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>varyHeaderValue</b>
The value of the HTTP Vary header for compressed responses. If this argument is not specified, a default value of "Accept-Encoding" will be used.

<b>externalCache</b>
Enable insertion of  Cache-Control: private response directive to indicate response message is intended for a single user and must not be cached by a shared or proxy cache.
Possible values: YES, NO
Default value: NO



##Example

set cmp param -cmpLevel bestspeed -quantumSize 20480

##unset cmp parameter

Reverts to the default value.Refer to the set cmp parameter command for meanings of the arguments.


##Synopsys

unset cmp parameter [-policyType] [-cmpLevel] [-quantumSize] [-serverCmp] [-minResSize] [-cmpBypassPct] [-cmpOnPush] [-addVaryHeader] [-varyHeaderValue] [-externalCache]


##Example

unset cmp param -policytype

##show cmp parameter

Displays the values of the compression parameters. Example: > show cmp parameterConfigured compression parameters:        Compression level: optimal        Quantum size: 4555        Server-side compression: ON        Minimum HTTP response size for compression: 0        CPU load at which to bypass compression: 100%        Compression on PUSH: DISABLED        Compression policy type: CLASSIC        Vary header insertion: DISABLED        Disable external cache: NO


##Synopsys

show cmp parameter


##Outputs

<b>cmpLevel</b>
Specify a compression level. Available settings function as follows:
 * Optimal - Corresponds to a gzip GZIP level of 5-7.
 * Best speed - Corresponds to a gzip level of 1.
 * Best compression - Corresponds to a gzip level of 9.

<b>quantumSize</b>
Minimum quantum of data to be filled before compression begins.

<b>serverCmp</b>
Compression enabled/disabled at back-end server.

<b>heurExpiry</b>
Heuristic basefile expiry.

<b>heurExpiryThres</b>
Threshold compression ratio for heuristic basefile expiry, multiplied by 100. For example, to set the threshold ratio to 1.25, specify 125.

<b>heurExpiryHistWt</b>
For heuristic basefile expiry, weightage to be given to historical delta compression ratio, specified as percentage.  For example, to give 25% weightage to historical ratio (and therefore 75% weightage to the ratio for current delta compression transaction), specify 25.

<b>minResSize</b>
Smallest response size, in bytes, to be compressed.

<b>cmpBypassPct</b>
NetScaler CPU threshold after which compression is not performed. Range: 0 - 100

<b>cmpOnPush</b>
NetScaler appliance does not wait for the quantum to be filled before starting to compress data. Upon receipt of a packet with a PUSH flag, the appliance immediately begins compression of the accumulated packets.

<b>policyType</b>
Type of policy. Available settings function as follows:
 * Classic -  Classic policies evaluate basic characteristics of traffic and other data.
 * Advanced -  Advanced policies (which have been renamed as default syntax policies) can perform the same type of evaluations as classic policies. They also enable you to analyze more data (for example, the body of an HTTP request) and to configure more operations in the policy rule (for example, transforming data in the body of a request into an HTTP header).

<b>addVaryHeader</b>
Control insertion of the Vary header in HTTP responses compressed by NetScaler. Intermediate caches store different versions of the response for different values of the headers present in the Vary response header.

<b>varyHeaderValue</b>
The value of the HTTP Vary header for compressed responses. If this argument is not specified, a default value of "Accept-Encoding" will be used.

<b>externalCache</b>
Enable insertion of  Cache-Control: private response directive to indicate response message is intended for a single user and must not be cached by a shared or proxy cache.

<b>builtin</b>
Flag to determine whether compression is default or not



