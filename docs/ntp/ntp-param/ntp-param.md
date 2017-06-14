#ntp param

The following operations can be performed on "ntp param":


[set](#set-ntp-param) | [unset](#unset-ntp-param) | [show](#show-ntp-param)

##set ntp param

Modifies the values for NTP parameters on the NetScaler appliance.


##Synopsys

set ntp param [-authentication ( YES | NO )] [-trustedkey &lt;positive_integer> ...] [-autokeyLogsec &lt;positive_integer>] [-revokeLogsec &lt;positive_integer>]


##Arguments

<b>authentication</b>
Apply NTP authentication, which enables the NTP client (NetScaler) to verify that the server is in fact known and trusted.
Possible values: YES, NO
Default value: YES

<b>trustedkey</b>
Key identifiers that are trusted for server authentication with symmetric key cryptography in the keys file.
Minimum value: 1
Maximum value: 65534

<b>autokeyLogsec</b>
Autokey protocol requires the keys to be refreshed periodically. This parameter specifies the interval between regenerations of new session keys. In seconds, expressed as a power of 2.
Default value: 12
Maximum value: 32

<b>revokeLogsec</b>
Interval between re-randomizations of the autokey seeds to prevent brute-force attacks on the autokey algorithms.
Default value: 16
Maximum value: 32



##unset ntp param

Use this command to remove ntp param settings.Refer to the set ntp param command for meanings of the arguments.


##Synopsys

unset ntp param [-authentication] [-trustedkey] [-autokeyLogsec] [-revokeLogsec]


##show ntp param

Displays information about the NTP parameters.


##Synopsys

show ntp param


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>authentication</b>
Apply NTP authentication, which enables the NTP client (NetScaler) to verify that the server is in fact known and trusted.

<b>trustedkey</b>
Key identifiers that are trusted for server authentication with symmetric key cryptography in the keys file.

<b>autokeyLogsec</b>
Autokey protocol requires the keys to be refreshed periodically. This parameter specifies the interval between regenerations of new session keys. In seconds, expressed as a power of 2.

<b>revokeLogsec</b>
Interval between re-randomizations of the autokey seeds to prevent brute-force attacks on the autokey algorithms.



