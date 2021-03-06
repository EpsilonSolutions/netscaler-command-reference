#bfd session

The following operations can be performed on "bfd session":


##show bfd session

Displays the details of the BFD sessions configured in the PE


##Synopsys

show bfd session [-localIP &lt;ip_addr|ipv6_addr>  [-remoteIP &lt;ip_addr|ipv6_addr>]]


##Arguments

<b>localIP</b>
IPV4 or IPV6 Address of Local Node

<b>remoteIP</b>
IPV4 or IPV6 Address of Remote Node



##Outputs

<b>state</b>
Current state of the BFD session

<b>localPort</b>
Source Port used by Local node to send Control packets for the BFD session

<b>RemotePort</b>
Source Port used by Remote node to send Control packets for the BFD session

<b>minimumTransmitInterval</b>
Minimum trasmit interval, in milliseconds, the local node would like to use when transmitting BFD Control packets

<b>negotiatedMinimumTransmitInterval</b>
Negotiated Minimum Transmit Interval. This is the interval at which the local node will be sending out BFD control packets

<b>minimumReceiveInterval</b>
Minimum receive interval, in milliseconds, between received BFD Control packets that the local node is capable of supporting

<b>negotiatedMinimumReceiveInterval</b>
Negotiated Minimum Receive Interval. This is the interval at which the local node will be expecting BFD control packets

<b>multiplier</b>
Detection Multiplier. The negotiated transmit interval multiplied by Detection multiplier provides the Detection Time for the remote node for the BFD session.

<b>remoteMultiplier</b>
Your Multiplier. The negotiated receive interval multiplied by Your Multiplier provides the Detection Time for the local node for the BFD session

<b>vlan</b>
VLAN ID on which the BDS session is configured

<b>localDiagnotic</b>
Diagnostic Code specifying the local system's reason for the last change in session state

<b>localDiscriminator</b>
A unique discriminator value generated by the local node for the session

<b>remoteDiscriminator</b>
A unique discriminator value as received from the remote node for the session

<b>passive</b>
Flag indicating that the session is passive

<b>multihop</b>
Flag indicating if the session is multihop

<b>adminDown</b>
Flag indicating if admin down is being sent

<b>originalOwnerPE</b>
Original Owner PE of the BFD session

<b>currentOwnerPE</b>
Current Owner PE of the BFD session

<b>stateflag</b>

<b>ownerNode</b>
The owner node in a Cluster for this BFD session. Owner node can vary from 0 to 31. If ownernode is not specified then the session is treated as Striped session.

<b>devno</b>

<b>count</b>



