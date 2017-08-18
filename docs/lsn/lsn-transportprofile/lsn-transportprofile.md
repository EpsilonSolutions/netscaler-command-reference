#lsn transportprofile

The following operations can be performed on "lsn transportprofile":


[add](#add-lsn-transportprofile) | [rm](#rm-lsn-transportprofile) | [set](#set-lsn-transportprofile) | [unset](#unset-lsn-transportprofile) | [show](#show-lsn-transportprofile)

##add lsn transportprofile

Add LSN Transport Profile.


##Synopsys

add lsn transportprofile &lt;transportprofilename> &lt;transportprotocol> [-sessiontimeout &lt;secs>] [-finrsttimeout &lt;secs>] [-stuntimeout &lt;positive_integer>] [-synidletimeout &lt;positive_integer>] [-portquota &lt;positive_integer>] [-sessionquota &lt;positive_integer>] [-groupSessionLimit &lt;positive_integer>] [-portpreserveparity ( ENABLED | DISABLED )] [-portpreserverange ( ENABLED | DISABLED )] [-syncheck ( ENABLED | DISABLED )]


##Arguments

<b>transportprofilename</b>
Name for the LSN transport profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN transport profile is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn transport profile1" or 'lsn transport profile1').

<b>transportprotocol</b>
Protocol for which to set the LSN transport profile parameters.
Possible values: TCP, UDP, ICMP

<b>sessiontimeout</b>
Timeout, in seconds, for an idle LSN session. If an LSN session is idle for a time that exceeds this value, the NetScaler ADC removes the session.
This timeout does not apply for a TCP LSN session when a FIN or RST message is received from either of the endpoints. 
Default value: 120
Minimum value: 60

<b>finrsttimeout</b>
Timeout, in seconds, for a TCP LSN session after a FIN or RST message is received from one of the endpoints.
If a TCP LSN session is idle (after the NetScaler ADC receives a FIN or RST message) for a time that exceeds this value, the NetScaler ADC removes the session.
Since the LSN feature of the NetScaler ADC does not maintain state information of any TCP LSN sessions, this timeout accommodates the transmission of the FIN or RST, and ACK messages from the other endpoint so that both endpoints can properly close the connection.
Default value: 30

<b>stuntimeout</b>
STUN protocol timeout
Default value: 600
Minimum value: 120
Maximum value: 1200

<b>synidletimeout</b>
SYN Idle timeout
Default value: 60
Minimum value: 30
Maximum value: 120

<b>portquota</b>
Maximum number of LSN NAT ports to be used at a time by each subscriber for the specified protocol. For example, each subscriber can be limited to a maximum of 500 TCP NAT ports. When the LSN NAT mappings for a subscriber reach the limit, the NetScaler ADC does not allocate additional NAT ports for that subscriber.
Default value: 0
Minimum value: 0
Maximum value: 65535

<b>sessionquota</b>
Maximum number of concurrent LSN sessions allowed for each subscriber for the specified protocol. 
When the number of LSN sessions reaches the limit for a subscriber, the NetScaler ADC does not allow the subscriber to open additional sessions.
Default value: 0
Minimum value: 0
Maximum value: 65535

<b>groupSessionLimit</b>
Maximum number of concurrent LSN sessions(for the specified protocol) allowed for all subscriber of a group to which this profile has bound. This limit will get split across the netscalers packet engines and rounded down. When the number of LSN sessions reaches the limit for a group in packet engine, the NetScaler ADC does not allow the subscriber of that group to open additional sessions through that packet engine.
Default value: 0
Minimum value: 0

<b>portpreserveparity</b>
Enable port parity between a subscriber port and its mapped LSN NAT port. For example, if a subscriber initiates a connection from an odd numbered port, the NetScaler ADC allocates an odd numbered LSN NAT port for this connection. 
You must set this parameter for proper functioning of protocols that require the source port to be even or odd numbered, for example, in peer-to-peer applications that use RTP or RTCP protocol.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>portpreserverange</b>
If a subscriber initiates a connection from a well-known port (0-1023), allocate a NAT port from the well-known port range (0-1023) for this connection. For example, if a subscriber initiates a connection from port 80, the NetScaler ADC can allocate port 100 as the NAT port for this connection.
This parameter applies to dynamic NAT without port block allocation. It also applies to Deterministic NAT if the range of ports allocated includes well-known ports.
When all the well-known ports of all the available NAT IP addresses are used in different subscriber's connections (LSN sessions), and a subscriber initiates a connection from a well-known port, the NetScaler ADC drops this connection.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>syncheck</b>
Silently drop any non-SYN packets for connections for which there is no LSN-NAT session present on the NetScaler ADC. 
If you disable this parameter, the NetScaler ADC accepts any non-SYN packets and creates a new LSN session entry for this connection. 
Following are some reasons for the NetScaler ADC to receive such packets:
* LSN session for a connection existed but the NetScaler ADC removed this session because the LSN session was idle for a time that exceeded the configured session timeout.
* Such packets can be a part of a DoS attack.
Possible values: ENABLED, DISABLED
Default value: ENABLED



##Example

add lsn transportprofile profile1 TCP -portquota 128

##rm lsn transportprofile

Remove LSN Transport Profile.


##Synopsys

rm lsn transportprofile &lt;transportprofilename>


##Arguments

<b>transportprofilename</b>
Name for the LSN transport profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN transport profile is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn transport profile1" or 'lsn transport profile1').



##Example

rm lsn transportprofile profile1 

##set lsn transportprofile

Set  LSN Transport Profile.


##Synopsys

set lsn transportprofile &lt;transportprofilename> [-sessiontimeout &lt;secs>] [-finrsttimeout &lt;secs>] [-stuntimeout &lt;positive_integer>] [-synidletimeout &lt;positive_integer>] [-portquota &lt;positive_integer>] [-sessionquota &lt;positive_integer>] [-groupSessionLimit &lt;positive_integer>] [-portpreserveparity ( ENABLED | DISABLED )] [-portpreserverange ( ENABLED | DISABLED )] [-syncheck ( ENABLED | DISABLED )]


##Arguments

<b>transportprofilename</b>
Name for the LSN transport profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN transport profile is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn transport profile1" or 'lsn transport profile1').

<b>sessiontimeout</b>
Timeout, in seconds, for an idle LSN session. If an LSN session is idle for a time that exceeds this value, the NetScaler ADC removes the session.
This timeout does not apply for a TCP LSN session when a FIN or RST message is received from either of the endpoints. 
Default value: 120
Minimum value: 60

<b>finrsttimeout</b>
Timeout, in seconds, for a TCP LSN session after a FIN or RST message is received from one of the endpoints.
If a TCP LSN session is idle (after the NetScaler ADC receives a FIN or RST message) for a time that exceeds this value, the NetScaler ADC removes the session.
Since the LSN feature of the NetScaler ADC does not maintain state information of any TCP LSN sessions, this timeout accommodates the transmission of the FIN or RST, and ACK messages from the other endpoint so that both endpoints can properly close the connection.
Default value: 30

<b>stuntimeout</b>
STUN protocol timeout
Default value: 600
Minimum value: 120
Maximum value: 1200

<b>synidletimeout</b>
SYN Idle timeout
Default value: 60
Minimum value: 30
Maximum value: 120

<b>portquota</b>
Maximum number of LSN NAT ports to be used at a time by each subscriber for the specified protocol. For example, each subscriber can be limited to a maximum of 500 TCP NAT ports. When the LSN NAT mappings for a subscriber reach the limit, the NetScaler ADC does not allocate additional NAT ports for that subscriber.
Default value: 0
Minimum value: 0
Maximum value: 65535

<b>sessionquota</b>
Maximum number of concurrent LSN sessions allowed for each subscriber for the specified protocol. 
When the number of LSN sessions reaches the limit for a subscriber, the NetScaler ADC does not allow the subscriber to open additional sessions.
Default value: 0
Minimum value: 0
Maximum value: 65535

<b>groupSessionLimit</b>
Maximum number of concurrent LSN sessions(for the specified protocol) allowed for all subscriber of a group to which this profile has bound. This limit will get split across the netscalers packet engines and rounded down. When the number of LSN sessions reaches the limit for a group in packet engine, the NetScaler ADC does not allow the subscriber of that group to open additional sessions through that packet engine.
Default value: 0
Minimum value: 0

<b>portpreserveparity</b>
Enable port parity between a subscriber port and its mapped LSN NAT port. For example, if a subscriber initiates a connection from an odd numbered port, the NetScaler ADC allocates an odd numbered LSN NAT port for this connection. 
You must set this parameter for proper functioning of protocols that require the source port to be even or odd numbered, for example, in peer-to-peer applications that use RTP or RTCP protocol.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>portpreserverange</b>
If a subscriber initiates a connection from a well-known port (0-1023), allocate a NAT port from the well-known port range (0-1023) for this connection. For example, if a subscriber initiates a connection from port 80, the NetScaler ADC can allocate port 100 as the NAT port for this connection.
This parameter applies to dynamic NAT without port block allocation. It also applies to Deterministic NAT if the range of ports allocated includes well-known ports.
When all the well-known ports of all the available NAT IP addresses are used in different subscriber's connections (LSN sessions), and a subscriber initiates a connection from a well-known port, the NetScaler ADC drops this connection.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>syncheck</b>
Silently drop any non-SYN packets for connections for which there is no LSN-NAT session present on the NetScaler ADC. 
If you disable this parameter, the NetScaler ADC accepts any non-SYN packets and creates a new LSN session entry for this connection. 
Following are some reasons for the NetScaler ADC to receive such packets:
* LSN session for a connection existed but the NetScaler ADC removed this session because the LSN session was idle for a time that exceeded the configured session timeout.
* Such packets can be a part of a DoS attack.
Possible values: ENABLED, DISABLED
Default value: ENABLED



##Example

set lsn transportprofile profile1 -portquota 128

##unset lsn transportprofile

Use this command to remove lsn transportprofile settings.Refer to the set lsn transportprofile command for meanings of the arguments.


##Synopsys

unset lsn transportprofile &lt;transportprofilename> [-sessiontimeout] [-finrsttimeout] [-stuntimeout] [-synidletimeout] [-portquota] [-sessionquota] [-groupSessionLimit] [-portpreserveparity] [-portpreserverange] [-syncheck]


##show lsn transportprofile

Display LSN Transport Profile.


##Synopsys

show lsn transportprofile [&lt;transportprofilename>]


##Arguments

<b>transportprofilename</b>
Name for the LSN transport profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN transport profile is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn transport profile1" or 'lsn transport profile1').



##Outputs

<b>transportprotocol</b>
Protocol for which to set the LSN transport profile parameters.

<b>sessiontimeout</b>
Timeout, in seconds, for an idle LSN session. If an LSN session is idle for a time that exceeds this value, the NetScaler ADC removes the session.
This timeout does not apply for a TCP LSN session when a FIN or RST message is received from either of the endpoints.

<b>finrsttimeout</b>
Timeout, in seconds, for a TCP LSN session after a FIN or RST message is received from one of the endpoints.
If a TCP LSN session is idle (after the NetScaler ADC receives a FIN or RST message) for a time that exceeds this value, the NetScaler ADC removes the session.
Since the LSN feature of the NetScaler ADC does not maintain state information of any TCP LSN sessions, this timeout accommodates the transmission of the FIN or RST, and ACK messages from the other endpoint so that both endpoints can properly close the connection.

<b>stuntimeout</b>
STUN protocol timeout

<b>synidletimeout</b>
SYN Idle timeout

<b>portquota</b>
Maximum number of LSN NAT ports to be used at a time by each subscriber for the specified protocol. For example, each subscriber can be limited to a maximum of 500 TCP NAT ports. When the LSN NAT mappings for a subscriber reach the limit, the NetScaler ADC does not allocate additional NAT ports for that subscriber.

<b>sessionquota</b>
Maximum number of concurrent LSN sessions allowed for each subscriber for the specified protocol. 
When the number of LSN sessions reaches the limit for a subscriber, the NetScaler ADC does not allow the subscriber to open additional sessions.

<b>groupSessionLimit</b>
Maximum number of concurrent LSN sessions(for the specified protocol) allowed for all subscriber of a group to which this profile has bound. This limit will get split across the netscalers packet engines and rounded down. When the number of LSN sessions reaches the limit for a group in packet engine, the NetScaler ADC does not allow the subscriber of that group to open additional sessions through that packet engine.

<b>portpreserveparity</b>
Enable port parity between a subscriber port and its mapped LSN NAT port. For example, if a subscriber initiates a connection from an odd numbered port, the NetScaler ADC allocates an odd numbered LSN NAT port for this connection. 
You must set this parameter for proper functioning of protocols that require the source port to be even or odd numbered, for example, in peer-to-peer applications that use RTP or RTCP protocol.

<b>portpreserverange</b>
If a subscriber initiates a connection from a well-known port (0-1023), allocate a NAT port from the well-known port range (0-1023) for this connection. For example, if a subscriber initiates a connection from port 80, the NetScaler ADC can allocate port 100 as the NAT port for this connection.
This parameter applies to dynamic NAT without port block allocation. It also applies to Deterministic NAT if the range of ports allocated includes well-known ports.
When all the well-known ports of all the available NAT IP addresses are used in different subscriber's connections (LSN sessions), and a subscriber initiates a connection from a well-known port, the NetScaler ADC drops this connection.

<b>syncheck</b>
Silently drop any non-SYN packets for connections for which there is no LSN-NAT session present on the NetScaler ADC. 
If you disable this parameter, the NetScaler ADC accepts any non-SYN packets and creates a new LSN session entry for this connection. 
Following are some reasons for the NetScaler ADC to receive such packets:
* LSN session for a connection existed but the NetScaler ADC removed this session because the LSN session was idle for a time that exceeded the configured session timeout.
* Such packets can be a part of a DoS attack.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show lsn transportprofile profile1

