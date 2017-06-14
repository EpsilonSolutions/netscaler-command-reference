#ipsec parameter

The following operations can be performed on "ipsec parameter":


[set](#set-ipsec-parameter) | [unset](#unset-ipsec-parameter) | [show](#show-ipsec-parameter)

##set ipsec parameter

Set global parameters for IPSEC


##Synopsys

set ipsec parameter [-ikeVersion ( V1 | V2 )] [-encAlgo ( AES | 3DES ) ...] [-hashAlgo &lt;hashAlgo> ...] [-lifetime &lt;positive_integer>] [-livenessCheckInterval &lt;positive_integer>] [-replayWindowSize &lt;positive_integer>] [-ikeRetryInterval &lt;positive_integer>] [-retransmissiontime &lt;positive_integer>]


##Arguments

<b>ikeVersion</b>
IKE Protocol Version
Possible values: V1, V2
Default value: KMP_IKEV2

<b>encAlgo</b>
Type of encryption algorithm
Default value: ENC_AES

<b>hashAlgo</b>
Type of hashing algorithm
Default value: HMAC_SHA256

<b>lifetime</b>
Lifetime of SA in seconds
Minimum value: 60
Maximum value: 31536000

<b>livenessCheckInterval</b>
Number of seconds after which a notify payload is sent to check the liveliness of the peer. Additional retries are done as per retransmit interval setting. Zero value disables liveliness checks.
Minimum value: 0
Maximum value: 64999

<b>replayWindowSize</b>
IPSec Replay window size for the data traffic
Minimum value: 0
Maximum value: 16384

<b>ikeRetryInterval</b>
IKE retry interval for bringing up the connection
Minimum value: 60
Maximum value: 3600

<b>retransmissiontime</b>
The interval in seconds to retry sending the IKE messages to peer, three consecutive attempts are done with doubled interval after every failure.,
increases for every retransmit till 6 retransmits. 
Minimum value: 1
Maximum value: 99



##unset ipsec parameter

Set global parameters for IPSEC.Refer to the set ipsec parameter command for meanings of the arguments.


##Synopsys

unset ipsec parameter [-ikeVersion] [-encAlgo] [-hashAlgo] [-lifetime] [-livenessCheckInterval] [-replayWindowSize] [-ikeRetryInterval] [-retransmissiontime]


##show ipsec parameter

Show global parameters for IPSEC


##Synopsys

show ipsec parameter


##Arguments

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>ikeVersion</b>
IKE Protocol Version

<b>encAlgo</b>
Type of encryption algorithm

<b>hashAlgo</b>
Type of hashing algorithm

<b>lifetime</b>
Lifetime of SA in seconds

<b>livenessCheckInterval</b>
Number of seconds after which a notify payload is sent to check the liveliness of the peer. Additional retries are done as per retransmit interval setting. Zero value disables liveliness checks.

<b>replayWindowSize</b>
IPSec Replay window size for the data traffic

<b>ikeRetryInterval</b>
IKE retry interval for bringing up the connection

<b>retransmissiontime</b>
The interval in seconds to retry sending the IKE messages to peer, three consecutive attempts are done with doubled interval after every failure.,
increases for every retransmit till 6 retransmits.



