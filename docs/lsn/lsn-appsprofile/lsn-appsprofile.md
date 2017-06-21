#lsn appsprofile

The following operations can be performed on "lsn appsprofile":


[add](#add-lsn-appsprofile) | [rm](#rm-lsn-appsprofile) | [set](#set-lsn-appsprofile) | [unset](#unset-lsn-appsprofile) | [bind](#bind-lsn-appsprofile) | [unbind](#unbind-lsn-appsprofile) | [show](#show-lsn-appsprofile)

##add lsn appsprofile

Add LSN Application Profile.


##Synopsys

add lsn appsprofile &lt;appsprofilename> &lt;transportprotocol> [-ippooling ( PAIRED | RANDOM )] [-mapping &lt;mapping>] [-filtering &lt;filtering>] [-tcpproxy ( ENABLED | DISABLED )] [-td &lt;positive_integer>] [-l2info ( ENABLED | DISABLED )]


##Arguments

<b>appsprofilename</b>
Name for the LSN application profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN application profile is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn application profile1" or 'lsn application profile1').

<b>transportprotocol</b>
Name of the protocol for which the parameters of this LSN application profile applies.
Possible values: TCP, UDP, ICMP

<b>ippooling</b>
NAT IP address allocation options for sessions associated with the same subscriber.
Available options function as follows:
* Paired - The NetScaler ADC allocates the same NAT IP address for all sessions associated with the same subscriber. When all the ports of a NAT IP address are used in LSN sessions (for same or multiple subscribers), the NetScaler ADC drops any new connection from the subscriber.
* Random - The NetScaler ADC allocates random NAT IP addresses, from the pool, for different sessions associated with the same subscriber.
This parameter is applicable to dynamic NAT allocation only.
Possible values: PAIRED, RANDOM
Default value: RANDOM

<b>mapping</b>
Type of LSN mapping to apply to subsequent packets originating from the same subscriber IP address and port.
Consider an example of an LSN mapping that includes the mapping of the subscriber IP:port (X:x), NAT IP:port (N:n), and external host IP:port (Y:y).
Available options function as follows: 
* ENDPOINT-INDEPENDENT - Reuse the LSN mapping for subsequent packets sent from the same subscriber IP address and port (X:x) to any external IP address and port. 
* ADDRESS-DEPENDENT - Reuse the LSN mapping for subsequent packets sent from the same subscriber IP address and port (X:x) to the same external IP address (Y), regardless of the external port.
* ADDRESS-PORT-DEPENDENT - Reuse the LSN mapping for subsequent packets sent from the same internal IP address and port (X:x) to the same external IP address and port (Y:y) while the mapping is still active.
Possible values: ENDPOINT-INDEPENDENT, ADDRESS-DEPENDENT, ADDRESS-PORT-DEPENDENT
Default value: ADDRESS-PORT-DEPENDENT

<b>filtering</b>
Type of filter to apply to packets originating from external hosts.
Consider an example of an LSN mapping that includes the mapping of subscriber IP:port (X:x), NAT IP:port (N:n), and external host IP:port (Y:y).
Available options function as follows:
* ENDPOINT INDEPENDENT - Filters out only packets not destined to the subscriber IP address and port X:x, regardless of the external host IP address and port source (Z:z).  The NetScaler ADC forwards any packets destined to X:x.  In other words, sending packets from the subscriber to any external IP address is sufficient to allow packets from any external hosts to the subscriber.
* ADDRESS DEPENDENT - Filters out packets not destined to subscriber IP address and port X:x.  In addition, the ADC filters out packets from Y:y destined for the subscriber (X:x) if the client has not previously sent packets to Y:anyport (external port independent). In other words, receiving packets from a specific external host requires that the subscriber first send packets to that specific external host's IP address.
* ADDRESS PORT DEPENDENT (the default) - Filters out  packets not destined to subscriber IP address and port (X:x).  In addition, the NetScaler ADC filters out packets from Y:y destined for the subscriber (X:x) if the subscriber has not previously sent packets to Y:y.  In other words, receiving packets from a specific external host requires that the subscriber first send packets first to that external IP address and port.
Possible values: ENDPOINT-INDEPENDENT, ADDRESS-DEPENDENT, ADDRESS-PORT-DEPENDENT
Default value: ADDRESS-PORT-DEPENDENT

<b>tcpproxy</b>
Enable TCP proxy, which enables the NetScaler appliance to optimize the  TCP traffic by using Layer 4 features.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>td</b>
ID of the traffic domain through which the NetScaler ADC sends the outbound traffic after performing LSN. 
If you do not specify an ID, the ADC sends the outbound traffic through the default traffic domain, which has an ID of 0.
Default value: 65535
Minimum value: 0

<b>l2info</b>
Enable l2info by creating natpcbs for LSN, which enables the NetScaler appliance to use L2CONN/MBF with LSN.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

add lsn appsprofile profile1 TCP -mapping ENDPOINT-INDEPENDENT

##rm lsn appsprofile

Remove LSN Application Profile.


##Synopsys

rm lsn appsprofile &lt;appsprofilename>


##Arguments

<b>appsprofilename</b>
Name for the LSN application profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN application profile is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn application profile1" or 'lsn application profile1').



##Example

rm lsn appsprofile profile1 

##set lsn appsprofile

Set LSN Application Profile.


##Synopsys

set lsn appsprofile &lt;appsprofilename> [-ippooling ( PAIRED | RANDOM )] [-mapping &lt;mapping>] [-filtering &lt;filtering>] [-tcpproxy ( ENABLED | DISABLED )] [-td &lt;positive_integer>] [-l2info ( ENABLED | DISABLED )]


##Arguments

<b>appsprofilename</b>
Name for the LSN application profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN application profile is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn application profile1" or 'lsn application profile1').

<b>ippooling</b>
NAT IP address allocation options for sessions associated with the same subscriber.
Available options function as follows:
* Paired - The NetScaler ADC allocates the same NAT IP address for all sessions associated with the same subscriber. When all the ports of a NAT IP address are used in LSN sessions (for same or multiple subscribers), the NetScaler ADC drops any new connection from the subscriber.
* Random - The NetScaler ADC allocates random NAT IP addresses, from the pool, for different sessions associated with the same subscriber.
This parameter is applicable to dynamic NAT allocation only.
Possible values: PAIRED, RANDOM
Default value: RANDOM

<b>mapping</b>
Type of LSN mapping to apply to subsequent packets originating from the same subscriber IP address and port.
Consider an example of an LSN mapping that includes the mapping of the subscriber IP:port (X:x), NAT IP:port (N:n), and external host IP:port (Y:y).
Available options function as follows: 
* ENDPOINT-INDEPENDENT - Reuse the LSN mapping for subsequent packets sent from the same subscriber IP address and port (X:x) to any external IP address and port. 
* ADDRESS-DEPENDENT - Reuse the LSN mapping for subsequent packets sent from the same subscriber IP address and port (X:x) to the same external IP address (Y), regardless of the external port.
* ADDRESS-PORT-DEPENDENT - Reuse the LSN mapping for subsequent packets sent from the same internal IP address and port (X:x) to the same external IP address and port (Y:y) while the mapping is still active.
Possible values: ENDPOINT-INDEPENDENT, ADDRESS-DEPENDENT, ADDRESS-PORT-DEPENDENT
Default value: ADDRESS-PORT-DEPENDENT

<b>filtering</b>
Type of filter to apply to packets originating from external hosts.
Consider an example of an LSN mapping that includes the mapping of subscriber IP:port (X:x), NAT IP:port (N:n), and external host IP:port (Y:y).
Available options function as follows:
* ENDPOINT INDEPENDENT - Filters out only packets not destined to the subscriber IP address and port X:x, regardless of the external host IP address and port source (Z:z).  The NetScaler ADC forwards any packets destined to X:x.  In other words, sending packets from the subscriber to any external IP address is sufficient to allow packets from any external hosts to the subscriber.
* ADDRESS DEPENDENT - Filters out packets not destined to subscriber IP address and port X:x.  In addition, the ADC filters out packets from Y:y destined for the subscriber (X:x) if the client has not previously sent packets to Y:anyport (external port independent). In other words, receiving packets from a specific external host requires that the subscriber first send packets to that specific external host's IP address.
* ADDRESS PORT DEPENDENT (the default) - Filters out  packets not destined to subscriber IP address and port (X:x).  In addition, the NetScaler ADC filters out packets from Y:y destined for the subscriber (X:x) if the subscriber has not previously sent packets to Y:y.  In other words, receiving packets from a specific external host requires that the subscriber first send packets first to that external IP address and port.
Possible values: ENDPOINT-INDEPENDENT, ADDRESS-DEPENDENT, ADDRESS-PORT-DEPENDENT
Default value: ADDRESS-PORT-DEPENDENT

<b>tcpproxy</b>
Enable TCP proxy, which enables the NetScaler appliance to optimize the  TCP traffic by using Layer 4 features.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>td</b>
ID of the traffic domain through which the NetScaler ADC sends the outbound traffic after performing LSN. 
If you do not specify an ID, the ADC sends the outbound traffic through the default traffic domain, which has an ID of 0.
Default value: 65535
Minimum value: 0

<b>l2info</b>
Enable l2info by creating natpcbs for LSN, which enables the NetScaler appliance to use L2CONN/MBF with LSN.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

Set lsn appsprofile profile1  -mapping ENDPOINT-INDEPENDENT

##unset lsn appsprofile

Use this command to remove lsn appsprofile settings.Refer to the set lsn appsprofile command for meanings of the arguments.


##Synopsys

unset lsn appsprofile &lt;appsprofilename> [-ippooling] [-mapping] [-filtering] [-tcpproxy] [-td] [-l2info]


##bind lsn appsprofile

Bind LSN Application Profile.


##Synopsys

bind lsn appsprofile &lt;appsprofilename> &lt;lsnport>


##Arguments

<b>appsprofilename</b>
Name for the LSN application profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN application profile is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn application profile1" or 'lsn application profile1').

<b>lsnport</b>
Port numbers or range of port numbers to match against the destination port of the incoming packet from a subscriber. When the destination port is matched, the LSN application profile is applied for the LSN session. Separate a range of ports with a hyphen. For example, 40-90.



##Example

bind lsn appsprofile profile1 80-100 

##unbind lsn appsprofile

Unbind LSN Application Profile.


##Synopsys

unbind lsn appsprofile &lt;appsprofilename> [&lt;lsnport>]


##Arguments

<b>appsprofilename</b>
Name for the LSN application profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN application profile is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn application profile1" or 'lsn application profile1').

<b>lsnport</b>
Port numbers or range of port numbers to match against the destination port of the incoming packet from a subscriber. When the destination port is matched, the LSN application profile is applied for the LSN session. Separate a range of ports with a hyphen. For example, 40-90.



##Example

unbind lsn appsprofile profile1 80-100 

##show lsn appsprofile

Display LSN Application Profile.


##Synopsys

show lsn appsprofile [&lt;appsprofilename>]


##Arguments

<b>appsprofilename</b>
Name for the LSN application profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN application profile is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn application profile1" or 'lsn application profile1').



##Outputs

<b>lsnport</b>
Port numbers or range of port numbers to match against the destination port of the incoming packet from a subscriber. When the destination port is matched, the LSN application profile is applied for the LSN session. Separate a range of ports with a hyphen. For example, 40-90.

<b>transportprotocol</b>
Name of the protocol for which the parameters of this LSN application profile applies.

<b>ippooling</b>
NAT IP address allocation options for sessions associated with the same subscriber.
Available options function as follows:
* Paired - The NetScaler ADC allocates the same NAT IP address for all sessions associated with the same subscriber. When all the ports of a NAT IP address are used in LSN sessions (for same or multiple subscribers), the NetScaler ADC drops any new connection from the subscriber.
* Random - The NetScaler ADC allocates random NAT IP addresses, from the pool, for different sessions associated with the same subscriber.
This parameter is applicable to dynamic NAT allocation only.

<b>mapping</b>
Type of LSN mapping to apply to subsequent packets originating from the same subscriber IP address and port.
Consider an example of an LSN mapping that includes the mapping of the subscriber IP:port (X:x), NAT IP:port (N:n), and external host IP:port (Y:y).
Available options function as follows: 
* ENDPOINT-INDEPENDENT - Reuse the LSN mapping for subsequent packets sent from the same subscriber IP address and port (X:x) to any external IP address and port. 
* ADDRESS-DEPENDENT - Reuse the LSN mapping for subsequent packets sent from the same subscriber IP address and port (X:x) to the same external IP address (Y), regardless of the external port.
* ADDRESS-PORT-DEPENDENT - Reuse the LSN mapping for subsequent packets sent from the same internal IP address and port (X:x) to the same external IP address and port (Y:y) while the mapping is still active.

<b>filtering</b>
Type of filter to apply to packets originating from external hosts.
Consider an example of an LSN mapping that includes the mapping of subscriber IP:port (X:x), NAT IP:port (N:n), and external host IP:port (Y:y).
Available options function as follows:
* ENDPOINT INDEPENDENT - Filters out only packets not destined to the subscriber IP address and port X:x, regardless of the external host IP address and port source (Z:z).  The NetScaler ADC forwards any packets destined to X:x.  In other words, sending packets from the subscriber to any external IP address is sufficient to allow packets from any external hosts to the subscriber.
* ADDRESS DEPENDENT - Filters out packets not destined to subscriber IP address and port X:x.  In addition, the ADC filters out packets from Y:y destined for the subscriber (X:x) if the client has not previously sent packets to Y:anyport (external port independent). In other words, receiving packets from a specific external host requires that the subscriber first send packets to that specific external host's IP address.
* ADDRESS PORT DEPENDENT (the default) - Filters out  packets not destined to subscriber IP address and port (X:x).  In addition, the NetScaler ADC filters out packets from Y:y destined for the subscriber (X:x) if the subscriber has not previously sent packets to Y:y.  In other words, receiving packets from a specific external host requires that the subscriber first send packets first to that external IP address and port.

<b>tcpproxy</b>
Enable TCP proxy, which enables the NetScaler appliance to optimize the  TCP traffic by using Layer 4 features.

<b>td</b>
ID of the traffic domain through which the NetScaler ADC sends the outbound traffic after performing LSN. 
If you do not specify an ID, the ADC sends the outbound traffic through the default traffic domain, which has an ID of 0.

<b>l2info</b>
Enable l2info by creating natpcbs for LSN, which enables the NetScaler appliance to use L2CONN/MBF with LSN.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show lsn appsprofile profile1

