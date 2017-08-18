#user protocol

The following operations can be performed on "user protocol":


[add](#add-user-protocol) | [rm](#rm-user-protocol) | [set](#set-user-protocol) | [unset](#unset-user-protocol) | [show](#show-user-protocol)

##add user protocol

Add the user protocolExample: add user protocol MQTT -transporttype TCP -extension mqtt_logic


##Synopsys

add user protocol &lt;name> -transport ( TCP | SSL ) -extension &lt;string> [-comment &lt;string>]


##Arguments

<b>name</b>
Unique name for the user protocol. Not case sensitive. Must begin with an ASCII letter or underscore (_) character, and must consist only of ASCII alphanumeric or underscore characters.

<b>transport</b>
Transport layer's protocol.
Possible values: TCP, SSL

<b>extension</b>
Name of the extension to add parsing and runtime handling of the protocol packets.

<b>comment</b>
Any comments associated with the protocol.



##rm user protocol

Removes an user protocol.


##Synopsys

rm user protocol &lt;name>


##Arguments

<b>name</b>
Unique name for the user protocol. Not case sensitive. Must begin with an ASCII letter or underscore (_) character, and must consist only of ASCII alphanumeric or underscore characters.



##set user protocol

Modifies the specified parameters of an user protocol.


##Synopsys

set user protocol &lt;name> -comment &lt;string>


##Arguments

<b>name</b>
Unique name for the user protocol. Not case sensitive. Must begin with an ASCII letter or underscore (_) character, and must consist only of ASCII alphanumeric or underscore characters.

<b>comment</b>
Any comments associated with the protocol.



##unset user protocol

Use this command to remove user protocol settings.Refer to the set user protocol command for meanings of the arguments.


##Synopsys

unset user protocol &lt;name> -comment


##show user protocol

Displays information about the available user protocols.


##Synopsys

show user protocol [&lt;name>]


##Arguments

<b>name</b>
Unique name for the user protocol. Not case sensitive. Must begin with an ASCII letter or underscore (_) character, and must consist only of ASCII alphanumeric or underscore characters.



##Outputs

<b>transport</b>
Transport layer's protocol.

<b>extension</b>
Name of the extension to add parsing and runtime handling of the protocol packets.

<b>comment</b>
Any comments associated with the protocol.

<b>stateflag</b>

<b>devno</b>

<b>count</b>



