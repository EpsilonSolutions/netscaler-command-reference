#lsn sipalgprofile

The following operations can be performed on "lsn sipalgprofile":


[add](#add-lsn-sipalgprofile) | [set](#set-lsn-sipalgprofile) | [unset](#unset-lsn-sipalgprofile) | [show](#show-lsn-sipalgprofile) | [rm](#rm-lsn-sipalgprofile)

##add lsn sipalgprofile

Add LSN SIPALG Profile.


##Synopsys

add lsn sipalgprofile &lt;sipalgprofilename> [-dataSessionIdleTimeout &lt;positive_integer>] [-sipSessionTimeout &lt;positive_integer>] [-registrationTimeout &lt;positive_integer>] [-sipsrcportrange &lt;port[-port]>] [-sipdstportrange &lt;port[-port]>] [-openRegisterPinhole ( ENABLED | DISABLED )] [-openContactPinhole ( ENABLED | DISABLED )] [-openViaPinhole ( ENABLED | DISABLED )] [-openRecordRoutePinhole ( ENABLED | DISABLED )] -sipTransportProtocol ( TCP | UDP ) [-openRoutePinhole ( ENABLED | DISABLED )] [-rport ( ENABLED | DISABLED )]


##Arguments

<b>sipalgprofilename</b>
The name of the SIPALG Profile.

<b>dataSessionIdleTimeout</b>
Idle timeout for the data channel sessions in seconds.
Default value: 120
Minimum value: 0

<b>sipSessionTimeout</b>
SIP control channel session timeout in seconds.
Default value: 600
Minimum value: 0

<b>registrationTimeout</b>
SIP registration timeout in seconds.
Default value: 60
Minimum value: 0

<b>sipsrcportrange</b>
Source port range for SIP_UDP and SIP_TCP.

<b>sipdstportrange</b>
Destination port range for SIP_UDP and SIP_TCP.

<b>openRegisterPinhole</b>
ENABLE/DISABLE RegisterPinhole creation.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>openContactPinhole</b>
ENABLE/DISABLE ContactPinhole creation.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>openViaPinhole</b>
ENABLE/DISABLE ViaPinhole creation.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>openRecordRoutePinhole</b>
ENABLE/DISABLE RecordRoutePinhole creation.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>sipTransportProtocol</b>
SIP ALG Profile transport protocol type.
Possible values: TCP, UDP

<b>openRoutePinhole</b>
ENABLE/DISABLE RoutePinhole creation.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>rport</b>
ENABLE/DISABLE rport.
Possible values: ENABLED, DISABLED
Default value: ENABLED



##Example

add lsn sipalgprofile profile1

##set lsn sipalgprofile

Set LSN SIPALG Profile.


##Synopsys

set lsn sipalgprofile &lt;sipalgprofilename> [-dataSessionIdleTimeout &lt;positive_integer>] [-sipSessionTimeout &lt;positive_integer>] [-registrationTimeout &lt;positive_integer>] [-sipsrcportrange &lt;port[-port]>] [-sipdstportrange &lt;port[-port]>] [-openRegisterPinhole ( ENABLED | DISABLED )] [-openContactPinhole ( ENABLED | DISABLED )] [-openViaPinhole ( ENABLED | DISABLED )] [-openRecordRoutePinhole ( ENABLED | DISABLED )] [-sipTransportProtocol ( TCP | UDP )] [-openRoutePinhole ( ENABLED | DISABLED )] [-rport ( ENABLED | DISABLED )]


##Arguments

<b>sipalgprofilename</b>
The name of the SIPALG Profile.

<b>dataSessionIdleTimeout</b>
Idle timeout for the data channel sessions in seconds.
Default value: 120
Minimum value: 0

<b>sipSessionTimeout</b>
SIP control channel session timeout in seconds.
Default value: 600
Minimum value: 0

<b>registrationTimeout</b>
SIP registration timeout in seconds.
Default value: 60
Minimum value: 0

<b>sipsrcportrange</b>
Source port range for SIP_UDP and SIP_TCP.

<b>sipdstportrange</b>
Destination port range for SIP_UDP and SIP_TCP.

<b>openRegisterPinhole</b>
ENABLE/DISABLE RegisterPinhole creation.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>openContactPinhole</b>
ENABLE/DISABLE ContactPinhole creation.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>openViaPinhole</b>
ENABLE/DISABLE ViaPinhole creation.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>openRecordRoutePinhole</b>
ENABLE/DISABLE RecordRoutePinhole creation.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>sipTransportProtocol</b>
SIP ALG Profile transport protocol type.
Possible values: TCP, UDP

<b>openRoutePinhole</b>
ENABLE/DISABLE RoutePinhole creation.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>rport</b>
ENABLE/DISABLE rport.
Possible values: ENABLED, DISABLED
Default value: ENABLED



##Example

Set lsn sipalgprofile profile1

##unset lsn sipalgprofile

Use this command to remove lsn sipalgprofile settings.Refer to the set lsn sipalgprofile command for meanings of the arguments.


##Synopsys

unset lsn sipalgprofile &lt;sipalgprofilename> [-dataSessionIdleTimeout] [-sipSessionTimeout] [-registrationTimeout] [-sipsrcportrange] [-sipdstportrange] [-openRegisterPinhole] [-openContactPinhole] [-openViaPinhole] [-openRecordRoutePinhole] [-sipTransportProtocol] [-openRoutePinhole] [-rport]


##show lsn sipalgprofile

Display LSN SIPALG Profile.


##Synopsys

show lsn sipalgprofile [&lt;sipalgprofilename>]


##Arguments

<b>sipalgprofilename</b>
The name of the SIPALG Profile.



##Outputs

<b>dataSessionIdleTimeout</b>
Idle timeout for the data channel sessions in seconds.

<b>sipSessionTimeout</b>
SIP control channel session timeout in seconds.

<b>registrationTimeout</b>
SIP registration timeout in seconds.

<b>sipsrcportrange</b>
Source port range for SIP_UDP and SIP_TCP.

<b>sipdstportrange</b>
Destination port range for SIP_UDP and SIP_TCP.

<b>openRegisterPinhole</b>
ENABLE/DISABLE RegisterPinhole creation.

<b>openContactPinhole</b>
ENABLE/DISABLE ContactPinhole creation.

<b>openViaPinhole</b>
ENABLE/DISABLE ViaPinhole creation.

<b>openRecordRoutePinhole</b>
ENABLE/DISABLE RecordRoutePinhole creation.

<b>sipTransportProtocol</b>
SIP ALG Profile transport protocol type.

<b>openRoutePinhole</b>
ENABLE/DISABLE RoutePinhole creation.

<b>rport</b>
ENABLE/DISABLE rport.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show lsn sipalgprofile profile1

##rm lsn sipalgprofile

Remove LSN SIPALG Profile.


##Synopsys

rm lsn sipalgprofile &lt;sipalgprofilename>


##Arguments

<b>sipalgprofilename</b>
The name of the SIPALG Profile.



##Example

rm lsn sipalgprofile profile1 

