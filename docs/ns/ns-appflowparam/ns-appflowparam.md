#ns appflowParam

The following operations can be performed on "ns appflowParam":


[set](#set-ns-appflowparam) | [unset](#unset-ns-appflowparam) | [show](#show-ns-appflowparam)

##set ns appflowParam

Set AppFlow parameters. NOTE: This command is deprecated.


##Synopsys




##Arguments

<b>templateRefresh</b>
IPFIX template refresh interval (in seconds).
Default value: 600
Minimum value: 60
Maximum value: 3600

<b>udpPmtu</b>
MTU to be used for IPFIX UDP packets.
Default value: 1472
Minimum value: 128
Maximum value: 1472

<b>httpUrl</b>
Enable AppFlow HTTP URL logging.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>httpCookie</b>
Enable AppFlow HTTP cookie logging.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>httpReferer</b>
Enable AppFlow HTTP referer logging.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>httpMethod</b>
Enable AppFlow HTTP method logging.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>httpHost</b>
Enable AppFlow HTTP host logging.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>httpUserAgent</b>
Enable AppFlow HTTP user-agent logging.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>clientTrafficOnly</b>
Control whether AppFlow records should be generated only for client-side traffic.
Possible values: YES, NO
Default value: NO



##Example

set ns appflowParam -templateRefresh 240

##unset ns appflowParam

Use this command to remove ns appflowParam settings.Refer to the set ns appflowParam command for meanings of the arguments.NOTE: This command is deprecated.


##Synopsys




##show ns appflowParam

Display AppFlow parameters. NOTE: This command is deprecated.This command is deprecated in favor of 'show appflow param'


##Synopsys




##Outputs

<b>templateRefresh</b>
IPFIX template refresh interval (in seconds).

<b>udpPmtu</b>
MTU to be used for IPFIX UDP packets.

<b>httpUrl</b>
Enable AppFlow HTTP URL logging.

<b>httpCookie</b>
Enable AppFlow HTTP cookie logging.

<b>httpReferer</b>
Enable AppFlow HTTP referer logging.

<b>httpMethod</b>
Enable AppFlow HTTP method logging.

<b>httpHost</b>
Enable AppFlow HTTP host logging.

<b>httpUserAgent</b>
Enable AppFlow HTTP user-agent logging.

<b>clientTrafficOnly</b>
Control whether AppFlow records should be generated only for client-side traffic.



