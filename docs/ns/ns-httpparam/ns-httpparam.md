#ns httpParam

The following operations can be performed on "ns httpParam":


[set](#set-ns-httpparam) | [unset](#unset-ns-httpparam) | [show](#show-ns-httpparam)

##set ns httpParam

Sets the configurable HTTP parameters for the NetScaler appliance.


##Synopsys

set ns httpParam [-dropInvalReqs ( ON | OFF )] [-markHttp09Inval ( ON | OFF )] [-markConnReqInval ( ON | OFF )] [-insNsSrvrHdr ( ON | OFF )  [&lt;nsSrvrHdr>]] [-logErrResp ( ON | OFF )] [-conMultiplex ( ENABLED | DISABLED )] [-maxReusePool &lt;positive_integer>]


##Arguments

<b>dropInvalReqs</b>
Drop invalid HTTP requests or responses.
Possible values: ON, OFF
Default value: OFF

<b>markHttp09Inval</b>
Mark HTTP/0.9 requests as invalid.
Possible values: ON, OFF
Default value: OFF

<b>markConnReqInval</b>
Mark CONNECT requests as invalid.
Possible values: ON, OFF
Default value: OFF

<b>insNsSrvrHdr</b>
Enable or disable NetScaler server header insertion for NetScaler generated HTTP responses.
Possible values: ON, OFF
Default value: OFF

<b>nsSrvrHdr</b>
The server header value to be inserted. If no explicit header is specified then NSBUILD.RELEASE is used as default server header.

<b>logErrResp</b>
Server header value to be inserted.
Possible values: ON, OFF
Default value: ON

<b>conMultiplex</b>
Reuse server connections for requests from more than one client connections.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>maxReusePool</b>
Maximum limit on the number of connections, from the NetScaler to a particular server that are kept in the reuse pool. This setting is helpful for optimal memory utilization and for reducing the idle connections to the server just after the peak time.
Minimum value: 0
Maximum value: 360000



##Example

set ns httpParam -dropInvalReqs ON

##unset ns httpParam

Use this command to remove ns httpParam settings.Refer to the set ns httpParam command for meanings of the arguments.


##Synopsys

unset ns httpParam [-dropInvalReqs] [-markHttp09Inval] [-markConnReqInval] [-insNsSrvrHdr] [-nsSrvrHdr] [-logErrResp] [-conMultiplex] [-maxReusePool]


##show ns httpParam

Displays the HTTP parameters configured on the NetScaler appliance.


##Synopsys

show ns httpParam


##Outputs

<b>dropInvalReqs</b>
Drop invalid HTTP requests or responses.

<b>markHttp09Inval</b>
Mark HTTP/0.9 requests as invalid.

<b>markConnReqInval</b>
Mark CONNECT requests as invalid.

<b>insNsSrvrHdr</b>
Enable or disable NetScaler server header insertion for NetScaler generated HTTP responses.

<b>nsSrvrHdr</b>
The server header value to be inserted. If no explicit header is specified then NSBUILD.RELEASE is used as default server header.

<b>logErrResp</b>
Whether to log HTTP error responses

<b>conMultiplex</b>
Reuse server connections for requests from more than one client connections.

<b>maxReusePool</b>
Maximum limit on the number of connections, from the NetScaler to a particular server that are kept in the reuse pool. This setting is helpful for optimal memory utilization and for reducing the idle connections to the server just after the peak time.

<b>builtin</b>
Flag to determine if the http param is built-in or not



