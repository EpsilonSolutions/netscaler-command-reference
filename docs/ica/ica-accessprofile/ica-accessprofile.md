#ica accessprofile

The following operations can be performed on "ica accessprofile":


[add](#add-ica-accessprofile) | [rm](#rm-ica-accessprofile) | [set](#set-ica-accessprofile) | [unset](#unset-ica-accessprofile) | [show](#show-ica-accessprofile)

##add ica accessprofile

This command creates an ica accessprofile that specifies status of the features (DEFAULT/DISABLED).


##Synopsys

add ica accessprofile &lt;name> [-ConnectClientLPTPorts ( DEFAULT | DISABLED )] [-ClientAudioRedirection ( DEFAULT | DISABLED )] [-LocalRemoteDataSharing ( DEFAULT | DISABLED )] [-ClientClipboardRedirection ( DEFAULT | DISABLED )] [-ClientCOMPortRedirection ( DEFAULT | DISABLED )] [-ClientDriveRedirection ( DEFAULT | DISABLED )] [-ClientPrinterRedirection ( DEFAULT | DISABLED )] [-Multistream ( DEFAULT | DISABLED )] [-ClientUSBDriveRedirection ( DEFAULT | DISABLED )]


##Arguments

<b>name</b>
Name for the ICA accessprofile. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and
the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the ICA accessprofile is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my ica accessprofile" or 'my ica accessprofile').
Each of the features can be configured as DEFAULT/DISABLED.
Here, DISABLED means that the policy settings on the backend XenApp/XenDesktop server are overridden and the NetScaler makes the decision to deny access. Whereas DEFAULT means that the NetScaler allows the request to reach the XenApp/XenDesktop that takes the decision to allow/deny access based on the policy configured on it. For example, if ClientAudioRedirection is enabled on the backend XenApp/XenDesktop server, and the configured profile has ClientAudioRedirection as DISABLED, the NetScaler makes the decision to deny the request irrespective of the configuration on the backend. If the configured profile has ClientAudioRedirection as DEFAULT, then the NetScaler forwards the requests to the backend XenApp/XenDesktop server.It then makes the decision to allow/deny access based on the policy configured on it.

<b>ConnectClientLPTPorts</b>
Allow Default access/Disable automatic connection of LPT ports from the client when the user logs on
Possible values: DEFAULT, DISABLED
Default value: DISABLED

<b>ClientAudioRedirection</b>
Allow Default access/Disable applications hosted on the server to play sounds through a sound device installed on the client computer, also allows or prevents users to record audio input
Possible values: DEFAULT, DISABLED
Default value: DISABLED

<b>LocalRemoteDataSharing</b>
Allow Default access/Disable file/data sharing via the Reciever for HTML5
Possible values: DEFAULT, DISABLED
Default value: DISABLED

<b>ClientClipboardRedirection</b>
Allow Default access/Disable the clipboard on the client device to be mapped to the clipboard on the server
Possible values: DEFAULT, DISABLED
Default value: DISABLED

<b>ClientCOMPortRedirection</b>
Allow Default access/Disable COM port redirection to and from the client
Possible values: DEFAULT, DISABLED
Default value: DISABLED

<b>ClientDriveRedirection</b>
Allow Default access/Disables drive redirection to and from the client
Possible values: DEFAULT, DISABLED
Default value: DISABLED

<b>ClientPrinterRedirection</b>
Allow Default access/Disable client printers to be mapped to a server when a user logs on to a session
Possible values: DEFAULT, DISABLED
Default value: DISABLED

<b>Multistream</b>
Allow Default access/Disable the multistream feature for the specified users
Possible values: DEFAULT, DISABLED
Default value: DISABLED

<b>ClientUSBDriveRedirection</b>
Allow Default access/Disable the redirection of USB devices to and from the client
Possible values: DEFAULT, DISABLED
Default value: DISABLED



##Example

add ica accessprofile profile1 -ClientAudioRedirection DISABLED

##rm ica accessprofile

This command removes the specified ica accessprofile.


##Synopsys

rm ica accessprofile &lt;name>


##Arguments

<b>name</b>
Name of the ICA accessprofile.



##Example

rm ica accessprofile profile1

##set ica accessprofile

This command modifies the specified parameters of the specified ica accessprofile.


##Synopsys

set ica accessprofile &lt;name> [-ConnectClientLPTPorts ( DEFAULT | DISABLED )] [-ClientAudioRedirection ( DEFAULT | DISABLED )] [-LocalRemoteDataSharing ( DEFAULT | DISABLED )] [-ClientClipboardRedirection ( DEFAULT | DISABLED )] [-ClientCOMPortRedirection ( DEFAULT | DISABLED )] [-ClientDriveRedirection ( DEFAULT | DISABLED )] [-ClientPrinterRedirection ( DEFAULT | DISABLED )] [-Multistream ( DEFAULT | DISABLED )] [-ClientUSBDriveRedirection ( DEFAULT | DISABLED )]


##Arguments

<b>name</b>
Name of the profile that you want to modify.

<b>ConnectClientLPTPorts</b>
Allow Default access/Disable automatic connection of LPT ports from the client when the user logs on
Possible values: DEFAULT, DISABLED
Default value: DISABLED

<b>ClientAudioRedirection</b>
Allow Default access/Disable applications hosted on the server to play sounds through a sound device installed on the client computer, also allows or prevents users to record audio input
Possible values: DEFAULT, DISABLED
Default value: DISABLED

<b>LocalRemoteDataSharing</b>
Allow Default access/Disable file/data sharing via the Reciever for HTML5
Possible values: DEFAULT, DISABLED
Default value: DISABLED

<b>ClientClipboardRedirection</b>
Allow Default access/Disable the clipboard on the client device to be mapped to the clipboard on the server
Possible values: DEFAULT, DISABLED
Default value: DISABLED

<b>ClientCOMPortRedirection</b>
Allow Default access/Disable COM port redirection to and from the client
Possible values: DEFAULT, DISABLED
Default value: DISABLED

<b>ClientDriveRedirection</b>
Allow Default access/Disables drive redirection to and from the client
Possible values: DEFAULT, DISABLED
Default value: DISABLED

<b>ClientPrinterRedirection</b>
Allow Default access/Disable client printers to be mapped to a server when a user logs on to a session
Possible values: DEFAULT, DISABLED
Default value: DISABLED

<b>Multistream</b>
Allow Default access/Disable the multistream feature for the specified users
Possible values: DEFAULT, DISABLED
Default value: DISABLED

<b>ClientUSBDriveRedirection</b>
Allow Default access/Disable the redirection of USB devices to and from the client
Possible values: DEFAULT, DISABLED
Default value: DISABLED



##Example

set ica accessprofile profile1 -ClientAudioRedirection DEFAULT

##unset ica accessprofile

Use this command to remove ica accessprofile settings.Refer to the set ica accessprofile command for meanings of the arguments.


##Synopsys

unset ica accessprofile &lt;name> [-ConnectClientLPTPorts] [-ClientAudioRedirection] [-LocalRemoteDataSharing] [-ClientClipboardRedirection] [-ClientCOMPortRedirection] [-ClientDriveRedirection] [-ClientPrinterRedirection] [-Multistream] [-ClientUSBDriveRedirection]


##show ica accessprofile

Displays details of the specified ica accessprofile. If no accessprofile is specified, displays a list of ica accessprofiles on the NetScaler appliance.


##Synopsys

show ica accessprofile [&lt;name>]


##Arguments

<b>name</b>
Name of the ica accessprofile.



##Outputs

<b>stateflag</b>

<b>ConnectClientLPTPorts</b>
Allow Default access/Disable automatic connection of LPT ports from the client when the user logs on

<b>ClientAudioRedirection</b>
Allow Default access/Disable applications hosted on the server to play sounds through a sound device installed on the client computer, also allows or prevents users to record audio input

<b>LocalRemoteDataSharing</b>
Allow Default access/Disable file/data sharing via the Reciever for HTML5

<b>ClientClipboardRedirection</b>
Allow Default access/Disable the clipboard on the client device to be mapped to the clipboard on the server

<b>ClientCOMPortRedirection</b>
Allow Default access/Disable COM port redirection to and from the client

<b>ClientDriveRedirection</b>
Allow Default access/Disables drive redirection to and from the client

<b>ClientPrinterRedirection</b>
Allow Default access/Disable client printers to be mapped to a server when a user logs on to a session

<b>Multistream</b>
Allow Default access/Disable the multistream feature for the specified users

<b>ClientUSBDriveRedirection</b>
Allow Default access/Disable the redirection of USB devices to and from the client

<b>refCnt</b>
Number of entities using this accessprofile

<b>builtin</b>
Indicates that the ICA accessprofile is a built-in (SYSTEM INTERNAL) type.

<b>isDefault</b>
A value of true is returned if it is a default accessprofile

<b>devno</b>

<b>count</b>



##Example

sh ica accessprofile profile1

