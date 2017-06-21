#lsn rtspalgprofile

The following operations can be performed on "lsn rtspalgprofile":


[add](#add-lsn-rtspalgprofile) | [set](#set-lsn-rtspalgprofile) | [unset](#unset-lsn-rtspalgprofile) | [show](#show-lsn-rtspalgprofile) | [rm](#rm-lsn-rtspalgprofile)

##add lsn rtspalgprofile

Add LSN RTSPALG Profile.


##Synopsys

add lsn rtspalgprofile &lt;rtspalgprofilename> [-rtspIdleTimeout &lt;positive_integer>] -rtspportrange &lt;port[-port]> [-rtspTransportProtocol ( TCP | UDP )]


##Arguments

<b>rtspalgprofilename</b>
The name of the RTSPALG Profile.

<b>rtspIdleTimeout</b>
Idle timeout for the rtsp sessions in seconds.
Default value: 120
Minimum value: 0

<b>rtspportrange</b>
port for the RTSP

<b>rtspTransportProtocol</b>
RTSP ALG Profile transport protocol type.
Possible values: TCP, UDP
Default value: TCP



##Example

add lsn rtspalgprofile profile1

##set lsn rtspalgprofile

Set LSN RTSPALG Profile.


##Synopsys

set lsn rtspalgprofile &lt;rtspalgprofilename> [-rtspIdleTimeout &lt;positive_integer>] [-rtspportrange &lt;port[-port]>] [-rtspTransportProtocol ( TCP | UDP )]


##Arguments

<b>rtspalgprofilename</b>
The name of the RTSPALG Profile.

<b>rtspIdleTimeout</b>
Idle timeout for the rtsp sessions in seconds.
Default value: 120
Minimum value: 0

<b>rtspportrange</b>
port for the RTSP

<b>rtspTransportProtocol</b>
RTSP ALG Profile transport protocol type.
Possible values: TCP, UDP
Default value: TCP



##Example

Set lsn rtspalgprofile profile1

##unset lsn rtspalgprofile

Use this command to remove lsn rtspalgprofile settings.Refer to the set lsn rtspalgprofile command for meanings of the arguments.


##Synopsys

unset lsn rtspalgprofile &lt;rtspalgprofilename> [-rtspIdleTimeout] [-rtspportrange] [-rtspTransportProtocol]


##show lsn rtspalgprofile

Display LSN RTSPALG Profile.


##Synopsys

show lsn rtspalgprofile [&lt;rtspalgprofilename>]


##Arguments

<b>rtspalgprofilename</b>
The name of the RTSPALG Profile.



##Outputs

<b>rtspIdleTimeout</b>
Idle timeout for the rtsp sessions in seconds.

<b>rtspportrange</b>
port for the RTSP

<b>rtspTransportProtocol</b>
RTSP ALG Profile transport protocol type.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show lsn rtspalgprofile profile1

##rm lsn rtspalgprofile

Remove LSN RTSPALG Profile.


##Synopsys

rm lsn rtspalgprofile &lt;rtspalgprofilename>


##Arguments

<b>rtspalgprofilename</b>
The name of the RTSPALG Profile.



##Example

rm lsn rtspalgprofile profile1 

