#rdp clientprofile

The following operations can be performed on "rdp clientprofile":


[add](#add-rdp-clientprofile) | [set](#set-rdp-clientprofile) | [unset](#unset-rdp-clientprofile) | [show](#show-rdp-clientprofile) | [rm](#rm-rdp-clientprofile)

##add rdp clientprofile

Add an rdp profile.


##Synopsys

add rdp clientprofile &lt;name> [-rdpUrlOverride ( ENABLE | DISABLE )] [-redirectClipboard ( ENABLE | DISABLE )] [-redirectDrives ( ENABLE | DISABLE )] [-redirectPrinters ( ENABLE | DISABLE )] [-redirectComPorts ( ENABLE | DISABLE )] [-redirectPnpDevices ( ENABLE | DISABLE )] [-keyboardHook &lt;keyboardHook>] [-audioCaptureMode ( ENABLE | DISABLE )] [-videoPlaybackMode ( ENABLE | DISABLE )] [-multiMonitorSupport ( ENABLE | DISABLE )] [-rdpCookieValidity &lt;positive_integer>] [-addUserNameInRdpFile ( YES | NO )] [-rdpFileName &lt;string>] [-rdpHost &lt;string>] [-rdpListener &lt;string>] [-rdpCustomParams &lt;string>] [-psk ]


##Arguments

<b>name</b>
The name of the rdp profile

<b>rdpUrlOverride</b>
This setting determines whether the RDP parameters supplied in the vpn url override those specified in the RDP profile.
Possible values: ENABLE, DISABLE
Default value: ENABLE

<b>redirectClipboard</b>
This setting corresponds to the Clipboard check box on the Local Resources tab under Options in RDC.
Possible values: ENABLE, DISABLE
Default value: ENABLE

<b>redirectDrives</b>
This setting corresponds to the selections for Drives under More on the Local Resources tab under Options in RDC.
Possible values: ENABLE, DISABLE
Default value: DISABLE

<b>redirectPrinters</b>
This setting corresponds to the selection in the Printers check box on the Local Resources tab under Options in RDC.
Possible values: ENABLE, DISABLE
Default value: ENABLE

<b>redirectComPorts</b>
This setting corresponds to the selections for comports under More on the Local Resources tab under Options in RDC.
Possible values: ENABLE, DISABLE
Default value: DISABLE

<b>redirectPnpDevices</b>
This setting corresponds to the selections for pnpdevices under More on the Local Resources tab under Options in RDC.
Possible values: ENABLE, DISABLE
Default value: DISABLE

<b>keyboardHook</b>
This setting corresponds to the selection in the Keyboard drop-down list on the Local Resources tab under Options in RDC.
Possible values: OnLocal, OnRemote, InFullScreenMode
Default value: InFullScreenMode

<b>audioCaptureMode</b>
This setting corresponds to the selections in the Remote audio area on the Local Resources tab under Options in RDC.
Possible values: ENABLE, DISABLE
Default value: DISABLE

<b>videoPlaybackMode</b>
This setting determines if Remote Desktop Connection (RDC) will use RDP efficient multimedia streaming for video playback.
Possible values: ENABLE, DISABLE
Default value: ENABLE

<b>multiMonitorSupport</b>
Enable/Disable Multiple Monitor Support for Remote Desktop Connection (RDC).
Possible values: ENABLE, DISABLE
Default value: ENABLE

<b>rdpCookieValidity</b>
RDP cookie validity period
Default value: 60
Minimum value: 60
Maximum value: 86400

<b>addUserNameInRdpFile</b>
Add username in rdp file.
Possible values: YES, NO
Default value: NO

<b>rdpFileName</b>
RDP file name to be sent to End User

<b>rdpHost</b>
Fully-qualified domain name (FQDN) of the RDP Listener.

<b>rdpListener</b>
Fully-qualified domain name (FQDN) of the RDP Listener with the port in the format FQDN:Port

<b>rdpCustomParams</b>
Option for RDP custom parameters settings (if any). Custom params needs to be separated by '&'
Default value: 0

<b>psk</b>
Pre shared key value
Default value: 0



##set rdp clientprofile

Modifies the specified parameters for RDP profile.


##Synopsys

set rdp clientprofile &lt;name> [-rdpUrlOverride ( ENABLE | DISABLE )] [-redirectClipboard ( ENABLE | DISABLE )] [-redirectDrives ( ENABLE | DISABLE )] [-redirectPrinters ( ENABLE | DISABLE )] [-redirectComPorts ( ENABLE | DISABLE )] [-redirectPnpDevices ( ENABLE | DISABLE )] [-keyboardHook &lt;keyboardHook>] [-audioCaptureMode ( ENABLE | DISABLE )] [-videoPlaybackMode ( ENABLE | DISABLE )] [-multiMonitorSupport ( ENABLE | DISABLE )] [-rdpCookieValidity &lt;positive_integer>] [-addUserNameInRdpFile ( YES | NO )] [-rdpFileName &lt;string>] [-rdpHost &lt;string>] [-rdpListener &lt;string>] [-rdpCustomParams &lt;string>] [-psk ]


##Arguments

<b>name</b>
The name of the rdp profile

<b>rdpUrlOverride</b>
This setting determines whether the RDP parameters supplied in the vpn url override those specified in the RDP profile.
Possible values: ENABLE, DISABLE
Default value: ENABLE

<b>redirectClipboard</b>
This setting corresponds to the Clipboard check box on the Local Resources tab under Options in RDC.
Possible values: ENABLE, DISABLE
Default value: ENABLE

<b>redirectDrives</b>
This setting corresponds to the selections for Drives under More on the Local Resources tab under Options in RDC.
Possible values: ENABLE, DISABLE
Default value: DISABLE

<b>redirectPrinters</b>
This setting corresponds to the selection in the Printers check box on the Local Resources tab under Options in RDC.
Possible values: ENABLE, DISABLE
Default value: ENABLE

<b>redirectComPorts</b>
This setting corresponds to the selections for comports under More on the Local Resources tab under Options in RDC.
Possible values: ENABLE, DISABLE
Default value: DISABLE

<b>redirectPnpDevices</b>
This setting corresponds to the selections for pnpdevices under More on the Local Resources tab under Options in RDC.
Possible values: ENABLE, DISABLE
Default value: DISABLE

<b>keyboardHook</b>
This setting corresponds to the selection in the Keyboard drop-down list on the Local Resources tab under Options in RDC.
Possible values: OnLocal, OnRemote, InFullScreenMode
Default value: InFullScreenMode

<b>audioCaptureMode</b>
This setting corresponds to the selections in the Remote audio area on the Local Resources tab under Options in RDC.
Possible values: ENABLE, DISABLE
Default value: DISABLE

<b>videoPlaybackMode</b>
This setting determines if Remote Desktop Connection (RDC) will use RDP efficient multimedia streaming for video playback.
Possible values: ENABLE, DISABLE
Default value: ENABLE

<b>multiMonitorSupport</b>
Enable/Disable Multiple Monitor Support for Remote Desktop Connection (RDC).
Possible values: ENABLE, DISABLE
Default value: ENABLE

<b>rdpCookieValidity</b>
RDP cookie validity period
Default value: 60
Minimum value: 60
Maximum value: 86400

<b>addUserNameInRdpFile</b>
Add username in rdp file.
Possible values: YES, NO
Default value: NO

<b>rdpFileName</b>
RDP file name to be sent to End User

<b>rdpHost</b>
Fully-qualified domain name (FQDN) of the RDP Listener.

<b>rdpListener</b>
Fully-qualified domain name (FQDN) of the RDP Listener with the port in the format FQDN:Port

<b>rdpCustomParams</b>
Option for RDP custom parameters settings (if any). Custom params needs to be separated by '&'
Default value: 0

<b>psk</b>
Pre shared key value
Default value: 0



##unset rdp clientprofile

Use this command to remove rdp clientprofile settings.Refer to the set rdp clientprofile command for meanings of the arguments.


##Synopsys

unset rdp clientprofile &lt;name> [-rdpUrlOverride] [-redirectClipboard] [-redirectDrives] [-redirectPrinters] [-redirectComPorts] [-redirectPnpDevices] [-keyboardHook] [-audioCaptureMode] [-videoPlaybackMode] [-multiMonitorSupport] [-rdpCookieValidity] [-addUserNameInRdpFile] [-rdpFileName] [-rdpHost] [-rdpListener] [-rdpCustomParams] [-psk]


##show rdp clientprofile

Display all rdp profiles


##Synopsys

show rdp clientprofile [&lt;name>]


##Arguments

<b>name</b>
The name of the rdp profile



##Outputs

<b>rdpUrlOverride</b>
This setting determines whether the RDP parameters supplied in the vpn url override those specified in the RDP profile.

<b>redirectClipboard</b>
This setting corresponds to the Clipboard check box on the Local Resources tab under Options in RDC.

<b>redirectDrives</b>
This setting corresponds to the selections for Drives under More on the Local Resources tab under Options in RDC.

<b>redirectPrinters</b>
This setting corresponds to the selection in the Printers check box on the Local Resources tab under Options in RDC.

<b>redirectComPorts</b>
This setting corresponds to the selections for comports under More on the Local Resources tab under Options in RDC.

<b>redirectPnpDevices</b>
This setting corresponds to the selections for pnpdevices under More on the Local Resources tab under Options in RDC.

<b>keyboardHook</b>
This setting corresponds to the selection in the Keyboard drop-down list on the Local Resources tab under Options in RDC.

<b>audioCaptureMode</b>
This setting corresponds to the selections in the Remote audio area on the Local Resources tab under Options in RDC.

<b>videoPlaybackMode</b>
This setting determines if Remote Desktop Connection (RDC) will use RDP efficient multimedia streaming for video playback.

<b>multiMonitorSupport</b>
Enable/Disable Multiple Monitor Support for Remote Desktop Connection (RDC).

<b>rdpCookieValidity</b>
RDP cookie validity period

<b>addUserNameInRdpFile</b>
Add username in rdp file.

<b>rdpFileName</b>
RDP file name to be sent to End User

<b>rdpHost</b>
Fully-qualified domain name (FQDN) of the RDP Listener.

<b>rdpListener</b>
Fully-qualified domain name (FQDN) of the RDP Listener with the port in the format FQDN:Port

<b>rdpCustomParams</b>
Option for RDP custom parameters settings (if any). Custom params needs to be separated by '&'

<b>psk</b>
Pre shared key value

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show rdp profile

##rm rdp clientprofile

Remove an rdp profile


##Synopsys

rm rdp clientprofile &lt;name>


##Arguments

<b>name</b>
The name of the rdp profile.



##Example

rm rdp profile 

