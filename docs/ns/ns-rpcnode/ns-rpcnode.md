#ns rpcNode

The following operations can be performed on "ns rpcNode":


[set](#set-ns-rpcnode) | [unset](#unset-ns-rpcnode) | [show](#show-ns-rpcnode)

##set ns rpcNode

Sets the authentication attributes associated with peer system node. All system nodes use Remote Procedure Calls (RPC) to communicate.


##Synopsys

set ns rpcNode &lt;IPAddress> {-password } [-srcIP &lt;ip_addr|ipv6_addr|*>] [-secure ( YES | NO )]


##Arguments

<b>IPAddress</b>
IP address of the node. This has to be in the same subnet as the NSIP address.

<b>password</b>
Password to be used in authentication with the peer system node.

<b>srcIP</b>
Source IP address to be used to communicate with the peer system node. The default value is 0, which means that the appliance uses the NSIP address as the source IP address.

<b>secure</b>
State of the channel when talking to the node.
Possible values: YES, NO



##Example

Example-1: Failover configurationIn a failover configuration define peer NS as:	  add node 1 10.101.4.87Set peer ha-unit's password as:	  set ns rpcnode 10.101.4.87 -password testpass -secure yesSystem will now use the configured password to authenticate with its failover unit.Example-2: GSLB configurationIn a GSLB configuration define peer NS GSLB site as:	  add gslb site us_east_coast remote 206.123.3.4Set peer GSLB-NS's password as:	  set ns rpcnode 206.123.3.4 -password testrunSystem will now use the configured password to authenticate with east-coast GSLB site.

##unset ns rpcNode

Use this command to remove ns rpcNode settings.Refer to the set ns rpcNode command for meanings of the arguments.


##Synopsys

unset ns rpcNode &lt;IPAddress> [-password] [-srcIP] [-secure]


##show ns rpcNode

Display a list of nodes currently communicating by using Remote Procedure Calls (RPC).


##Synopsys

show ns rpcNode [&lt;IPAddress>]


##Arguments

<b>IPAddress</b>
IP address of the node.



##Outputs

<b>password</b>
Password.

<b>srcIP</b>
The src ip used in communiction with the peer System node.

<b>secure</b>
State of the channel when talking to the node.

<b>flags</b>
Flags related to this rpcNode

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

Following example shows list of nodes communicating using RPC:&gt; sh rpcnode1)		IPAddress:	10.101.4.84 Password:  ..8a7b474124957776b56cf03b28 Srcip: 1.1.1.12)		IPAddress:	10.101.4.87 Password:  ..ca2a035465d22c 			Srcip: 2.2.2.2 Done

