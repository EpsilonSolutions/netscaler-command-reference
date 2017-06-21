#onLinkIPv6Prefix

The following operations can be performed on "onLinkIPv6Prefix":


[add](#add-onlinkipv6prefix) | [rm](#rm-onlinkipv6prefix) | [set](#set-onlinkipv6prefix) | [unset](#unset-onlinkipv6prefix) | [show](#show-onlinkipv6prefix)

##add onLinkIPv6Prefix

add a new on-link global prefix.


##Synopsys

add onLinkIPv6Prefix &lt;ipv6Prefix> [-onlinkPrefix ( YES | NO )] [-autonomusPrefix ( YES | NO )] [-depricatePrefix ( YES | NO )] [-decrementPrefixLifeTimes ( YES | NO )] [-prefixValideLifeTime &lt;positive_integer>] [-prefixPreferredLifeTime &lt;positive_integer>]


##Arguments

<b>ipv6Prefix</b>
Onlink prefixes for RA messages.

<b>onlinkPrefix</b>
RA Prefix onlink flag.
Possible values: YES, NO
Default value: YES

<b>autonomusPrefix</b>
RA Prefix Autonomus flag.
Possible values: YES, NO
Default value: YES

<b>depricatePrefix</b>
Depricate the prefix.
Possible values: YES, NO
Default value: NO

<b>decrementPrefixLifeTimes</b>
RA Prefix Autonomus flag.
Possible values: YES, NO
Default value: NO

<b>prefixValideLifeTime</b>
Valide life time of the prefix, in seconds.
Default value: 2592000
Minimum value: 0

<b>prefixPreferredLifeTime</b>
Preferred life time of the prefix, in seconds.
Default value: 604800
Minimum value: 0



##Example

add onLinkIPv6Prefix 8000::/64

##rm onLinkIPv6Prefix

remove an existing on-link global prefix.


##Synopsys

rm onLinkIPv6Prefix &lt;ipv6Prefix>


##Arguments

<b>ipv6Prefix</b>
Onlink prefixes for RA messages.



##Example

rm onLinkIPv6Prefix 8000::/64

##set onLinkIPv6Prefix

set on-link global prefix's configuration variables.


##Synopsys

set onLinkIPv6Prefix &lt;ipv6Prefix> [-onlinkPrefix ( YES | NO )] [-autonomusPrefix ( YES | NO )] [-depricatePrefix ( YES | NO )] [-decrementPrefixLifeTimes ( YES | NO )] [-prefixValideLifeTime &lt;positive_integer>] [-prefixPreferredLifeTime &lt;positive_integer>]


##Arguments

<b>ipv6Prefix</b>
Onlink prefixes for RA messages.

<b>onlinkPrefix</b>
RA Prefix onlink flag.
Possible values: YES, NO
Default value: YES

<b>autonomusPrefix</b>
RA Prefix Autonomus flag.
Possible values: YES, NO
Default value: YES

<b>depricatePrefix</b>
Depricate the prefix.
Possible values: YES, NO
Default value: NO

<b>decrementPrefixLifeTimes</b>
RA Prefix Autonomus flag.
Possible values: YES, NO
Default value: NO

<b>prefixValideLifeTime</b>
Valide life time of the prefix, in seconds.
Default value: 2592000
Minimum value: 0

<b>prefixPreferredLifeTime</b>
Preferred life time of the prefix, in seconds.
Default value: 604800
Minimum value: 0



##Example

set onLinkIPv6Prefix 8000::/64 -prefixValideLifeTime 2592000

##unset onLinkIPv6Prefix

Use this command to remove  onLinkIPv6Prefix settings.Refer to the set  onLinkIPv6Prefix command for meanings of the arguments.


##Synopsys

unset onLinkIPv6Prefix &lt;ipv6Prefix> [-onlinkPrefix] [-autonomusPrefix] [-depricatePrefix] [-decrementPrefixLifeTimes] [-prefixValideLifeTime] [-prefixPreferredLifeTime]


##show onLinkIPv6Prefix

displays on-link global prefixes.


##Synopsys

show onLinkIPv6Prefix [&lt;ipv6Prefix>]


##Arguments

<b>ipv6Prefix</b>
Onlink prefixes for RA messages.



##Outputs

<b>onlinkPrefix</b>
RA Prefix onlink flag.

<b>autonomusPrefix</b>
RA Prefix Autonomus flag.

<b>depricatePrefix</b>
Depricate the prefix.

<b>decrementPrefixLifeTimes</b>
RA Prefix Autonomus flag.

<b>prefixValideLifeTime</b>
Valide life time of the prefix, in seconds.

<b>prefixPreferredLifeTime</b>
Preferred life time of the prefix, in seconds.

<b>stateflag</b>
RA Param state flags

<b>prefixCurrValideLfT</b>
Prefix current valid life time

<b>prefixCurrPreferredLfT</b>
Prefix current prefered life time

<b>devno</b>

<b>count</b>



