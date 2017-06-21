#ssl dtlsProfile

The following operations can be performed on "ssl dtlsProfile":


[add](#add-ssl-dtlsprofile) | [rm](#rm-ssl-dtlsprofile) | [set](#set-ssl-dtlsprofile) | [unset](#unset-ssl-dtlsprofile) | [show](#show-ssl-dtlsprofile)

##add ssl dtlsProfile

Create a new DTLS profile on the NetScaler ADC.


##Synopsys

add ssl dtlsProfile &lt;name> [-pmtuDiscovery ( ENABLED | DISABLED )] [-maxRecordSize &lt;positive_integer>] [-maxRetryTime &lt;positive_integer>] [-helloVerifyRequest ( ENABLED | DISABLED )] [-terminateSession ( ENABLED | DISABLED )] [-maxPacketSize &lt;positive_integer>]


##Arguments

<b>name</b>
Name for the DTLS profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@),equals sign (=), and hyphen (-) characters. Cannot be changed after the profile is created.

<b>pmtuDiscovery</b>
Source for the maximum record size value. If ENABLED, the value is taken from the PMTU table. If DISABLED, the value is taken from the profile.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>maxRecordSize</b>
Maximum size of records that can be sent if PMTU is disabled.
Default value: 1459
Minimum value: 250
Maximum value: 1459

<b>maxRetryTime</b>
Wait for the specified time, in seconds, before resending the request.
Default value: 3
Minimum value: 0

<b>helloVerifyRequest</b>
Send a Hello Verify request to validate the client.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>terminateSession</b>
Terminate the session if the message authentication code (MAC) of the client and server do not match.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>maxPacketSize</b>
Maximum number of packets to reassemble. This value helps protect against a fragmented packet attack.
Default value: 120
Minimum value: 0
Maximum value: 86400



##Example

add dtlsProfile dtls1 -helloVerifyRequest  ENABLED -maxRetryTime 4

##rm ssl dtlsProfile

Remove a DTLS profile on the Netscaler


##Synopsys

rm ssl dtlsProfile &lt;name>


##Arguments

<b>name</b>
Name of the DTLS profile



##Example

rm dtlsprofile &lt;profile name&gt;

##set ssl dtlsProfile

Set/modify DTLS profile values


##Synopsys

set ssl dtlsProfile &lt;name> [-pmtuDiscovery ( ENABLED | DISABLED )] [-maxRecordSize &lt;positive_integer>] [-maxRetryTime &lt;positive_integer>] [-helloVerifyRequest ( ENABLED | DISABLED )] [-terminateSession ( ENABLED | DISABLED )] [-maxPacketSize &lt;positive_integer>]


##Arguments

<b>name</b>
Name for the DTLS profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@),equals sign (=), and hyphen (-) characters. Cannot be changed after the profile is created.

<b>pmtuDiscovery</b>
Source for the maximum record size value. If ENABLED, the value is taken from the PMTU table. If DISABLED, the value is taken from the profile.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>maxRecordSize</b>
Maximum size of records that can be sent if PMTU is disabled.
Default value: 1459
Minimum value: 250
Maximum value: 1459

<b>maxRetryTime</b>
Wait for the specified time, in seconds, before resending the request.
Default value: 3
Minimum value: 0

<b>helloVerifyRequest</b>
Send a Hello Verify request to validate the client.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>terminateSession</b>
Terminate the session if the message authentication code (MAC) of the client and server do not match.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>maxPacketSize</b>
Maximum number of packets to reassemble. This value helps protect against a fragmented packet attack.
Default value: 120
Minimum value: 0
Maximum value: 86400



##Example

set dtlsprofile &lt;profile name&gt; -dropInvalReqs ON -markHttp09Inval ON

##unset ssl dtlsProfile

Use this command to remove ssl dtlsProfile settings.Refer to the set ssl dtlsProfile command for meanings of the arguments.


##Synopsys

unset ssl dtlsProfile &lt;name> [-pmtuDiscovery] [-maxRecordSize] [-maxRetryTime] [-helloVerifyRequest] [-terminateSession] [-maxPacketSize]


##show ssl dtlsProfile

Display all the configured DTLS profiles in the system. If a name is specified, then only that profile is shown.


##Synopsys

show ssl dtlsProfile [&lt;name>]


##Arguments

<b>name</b>
Name of the DTLS profile.



##Outputs

<b>pmtuDiscovery</b>
PMTU Discovery

<b>maxRecordSize</b>
Maximum record size

<b>maxRetryTime</b>
Maximum retry time

<b>helloVerifyRequest</b>
Hello Verify Request

<b>terminateSession</b>
Terminate Session

<b>maxPacketSize</b>
Maximum Packet Size

<b>builtin</b>
Flag to determine whether dtls profile is built-in or not

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show dtls profile [profile name]

