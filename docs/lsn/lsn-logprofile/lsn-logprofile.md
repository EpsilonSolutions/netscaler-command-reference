#lsn logprofile

The following operations can be performed on "lsn logprofile":


[add](#add-lsn-logprofile) | [rm](#rm-lsn-logprofile) | [set](#set-lsn-logprofile) | [unset](#unset-lsn-logprofile) | [show](#show-lsn-logprofile)

##add lsn logprofile

Add LSN logging Profile.


##Synopsys

add lsn logprofile &lt;logProfileName> [-logSubscrInfo ( ENABLED | DISABLED )] [-logCompact ( ENABLED | DISABLED )]


##Arguments

<b>logProfileName</b>
The name of the logging Profile.

<b>logSubscrInfo</b>
Subscriber ID information is logged if option is enabled.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>logCompact</b>
Logs in Compact Logging format if option is enabled.
Possible values: ENABLED, DISABLED
Default value: ENABLED



##Example

add lsn logprofile profile1 -logSubscrInfo ENABLED

##rm lsn logprofile

Remove LSN logging Profile.


##Synopsys

rm lsn logprofile &lt;logProfileName>


##Arguments

<b>logProfileName</b>
The name of the logging Profile.



##Example

rm lsn logprofile profile1 

##set lsn logprofile

Set  LSN logging Profile.


##Synopsys

set lsn logprofile &lt;logProfileName> [-logSubscrInfo ( ENABLED | DISABLED )] [-logCompact ( ENABLED | DISABLED )]


##Arguments

<b>logProfileName</b>
The name of the logging Profile.

<b>logSubscrInfo</b>
Subscriber ID information is logged if option is enabled.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>logCompact</b>
Logs in Compact Logging format if option is enabled.
Possible values: ENABLED, DISABLED
Default value: ENABLED



##Example

set lsn logprofile profile1 -logSubscrInfo ENABLED

##unset lsn logprofile

Use this command to remove lsn logprofile settings.Refer to the set lsn logprofile command for meanings of the arguments.


##Synopsys

unset lsn logprofile &lt;logProfileName> [-logSubscrInfo] [-logCompact]


##show lsn logprofile

Display LSN logging Profile.


##Synopsys

show lsn logprofile [&lt;logProfileName>]


##Arguments

<b>logProfileName</b>
The name of the logging Profile.



##Outputs

<b>logSubscrInfo</b>
Subscriber ID information is logged if option is enabled.

<b>logCompact</b>
Logs in Compact Logging format if option is enabled.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show lsn logprofile profile1

