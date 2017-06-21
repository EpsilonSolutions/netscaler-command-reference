#ipsec profile

The following operations can be performed on "ipsec profile":


[add](#add-ipsec-profile) | [show](#show-ipsec-profile) | [rm](#rm-ipsec-profile)

##add ipsec profile

Add an ipsec profile.


##Synopsys

add ipsec profile &lt;name> [-ikeVersion ( V1 | V2 )] [-encAlgo ( AES | 3DES ) ...] [-hashAlgo &lt;hashAlgo> ...] [-lifetime &lt;positive_integer>] (-psk  | (-publickey &lt;string>  -privatekey &lt;string>  -peerPublicKey &lt;string>)) [-livenessCheckInterval &lt;positive_integer>] [-replayWindowSize &lt;positive_integer>] [-ikeRetryInterval &lt;positive_integer>] [-retransmissiontime &lt;positive_integer>] [-perfectForwardSecrecy ( ENABLE | DISABLE )]


##Arguments

<b>name</b>
The name of the ipsec profile

<b>ikeVersion</b>
IKE Protocol Version
Possible values: V1, V2

<b>encAlgo</b>
Type of encryption algorithm

<b>hashAlgo</b>
Type of hashing algorithm

<b>lifetime</b>
Lifetime of IKE SA in seconds. Lifetime of IPSec SA will be (lifetime of IKE SA/8)
Minimum value: 480
Maximum value: 31536000

<b>psk</b>
Pre shared key value

<b>publickey</b>
Public key file path

<b>privatekey</b>
Private key file path

<b>peerPublicKey</b>
Peer public key file path

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
The interval in seconds to retry sending the IKE messages to peer, three consecutive attempts are done with doubled interval after every failure.
Minimum value: 1
Maximum value: 99

<b>perfectForwardSecrecy</b>
Enable/Disable PFS.
Possible values: ENABLE, DISABLE



##show ipsec profile

Display all of the configured ipsec peers


##Synopsys

show ipsec profile [&lt;name>]


##Arguments

<b>name</b>
The name of the ipsec profile



##Outputs

<b>ikeVersion</b>
IKE Protocol Version

<b>encAlgo</b>
Type of encryption algorithm.

<b>hashAlgo</b>
Type of hashing algorithm

<b>lifetime</b>
Lifetime of IKE SA in seconds. Lifetime of IPSec SA will be (lifetime of IKE SA/8)

<b>livenessCheckInterval</b>
Number of seconds after which a notify payload is sent to check the liveliness of the peer. Additional retries are done as per retransmit interval setting. Zero value disables liveliness checks.

<b>replayWindowSize</b>
IPSec Replay window size for the data traffic

<b>retransmissiontime</b>
The interval in seconds to retry sending the IKE messages to peer, three consecutive attempts are done with doubled interval after every failure.

<b>psk</b>
Pre shared key value

<b>publickey</b>
Public key file path

<b>privatekey</b>
Private key file path

<b>peerPublicKey</b>
Peer public key file path

<b>ikeRetryInterval</b>
IKE retry interval for bringing up the connection

<b>perfectForwardSecrecy</b>
Enable/Disable PFS.

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show ipsec profile

##rm ipsec profile

Remove an ipsec peer


##Synopsys

rm ipsec profile &lt;name>


##Arguments

<b>name</b>
The name of the ipsec profile.



##Example

rm ipsec profile 

