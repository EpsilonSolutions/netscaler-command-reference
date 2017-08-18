#pcp profile

The following operations can be performed on "pcp profile":


[add](#add-pcp-profile) | [rm](#rm-pcp-profile) | [set](#set-pcp-profile) | [unset](#unset-pcp-profile) | [show](#show-pcp-profile)

##add pcp profile

Creates a pcp profile.


##Synopsys

add pcp profile &lt;name> [-mapping ( ENABLED | DISABLED )] [-peer ( ENABLED | DISABLED )] [-minMapLife &lt;secs>] [-maxMapLife &lt;secs>] [-announceMultiCount &lt;positive_integer>] [-thirdParty ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name for the PCP Profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my pcpProfile" or my pcpProfile).

<b>mapping</b>
This argument is for enabling/disabling the MAP opcode  of current PCP Profile
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>peer</b>
This argument is for enabling/disabling the PEER opcode of current PCP Profile
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>minMapLife</b>
Integer value that identify the minimum mapping lifetime (in seconds) for a pcp profile. default(120s)
Maximum value: 2147483647

<b>maxMapLife</b>
Integer value that identify the maximum mapping lifetime (in seconds) for a pcp profile. default(86400s = 24Hours).
Maximum value: 2147483647

<b>announceMultiCount</b>
Integer value that identify the number announce message to be send.
Default value: 10
Minimum value: 0
Maximum value: 65535

<b>thirdParty</b>
This argument is for enabling/disabling the THIRD PARTY opcode of current PCP Profile
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

add pcp profile  prof1

##rm pcp profile

Removes a  pcp profile from the NetScaler appliance.


##Synopsys

rm pcp profile &lt;name>@ ...


##Arguments

<b>name</b>
Name of the pcp server.



##Example

rm pcp profile prof1

##set pcp profile

Modifies the specified parameters of a  pcp profile.


##Synopsys

set pcp profile &lt;name> [-mapping ( ENABLED | DISABLED )] [-peer ( ENABLED | DISABLED )] [-minMapLife &lt;secs>] [-maxMapLife &lt;secs>] [-announceMultiCount &lt;positive_integer>] [-thirdParty ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name for the PCP Profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my pcpProfile" or my pcpProfile).

<b>mapping</b>
This argument is for enabling/disabling the MAP opcode  of current PCP Profile
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>peer</b>
This argument is for enabling/disabling the PEER opcode of current PCP Profile
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>minMapLife</b>
Integer value that identify the minimum mapping lifetime (in seconds) for a pcp profile. default(120s)
Maximum value: 2147483647

<b>maxMapLife</b>
Integer value that identify the maximum mapping lifetime (in seconds) for a pcp profile. default(86400s = 24Hours).
Maximum value: 2147483647

<b>announceMultiCount</b>
Integer value that identify the number announce message to be send.
Default value: 10
Minimum value: 0
Maximum value: 65535

<b>thirdParty</b>
This argument is for enabling/disabling the THIRD PARTY opcode of current PCP Profile
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

set pcp profile prof1  -MAPPING  ENABLED

##unset pcp profile

Use this command to remove pcp profile settings.Refer to the set pcp profile command for meanings of the arguments.


##Synopsys

unset pcp profile &lt;name> [-mapping] [-peer] [-minMapLife] [-maxMapLife] [-announceMultiCount] [-thirdParty]


##show pcp profile

Displays the  pcp server information.


##Synopsys

show pcp profile [&lt;name>]


##Arguments

<b>name</b>
Name of the pcp server.



##Outputs

<b>mapping</b>
This argument is for enabling/disabling the MAP opcode  of current PCP Profile

<b>peer</b>
This argument is for enabling/disabling the PEER opcode of current PCP Profile

<b>minMapLife</b>
Integer value that identify the minimum mapping lifetime (in seconds) for a pcp profile. default(120s)

<b>maxMapLife</b>
Integer value that identify the maximum mapping lifetime (in seconds) for a pcp profile. default(86400s = 24Hours).

<b>announceMultiCount</b>
Integer value that identify the number announce message to be send.

<b>thirdParty</b>
This argument is for enabling/disabling the THIRD PARTY opcode of current PCP Profile

<b>devno</b>

<b>count</b>

<b>stateflag</b>



