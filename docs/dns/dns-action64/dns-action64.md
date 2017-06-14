#dns action64

The following operations can be performed on "dns action64":


[add](#add-dns-action64) | [rm](#rm-dns-action64) | [set](#set-dns-action64) | [unset](#unset-dns-action64) | [show](#show-dns-action64)

##add dns action64

Add a dns64 action.


##Synopsys

add dns action64 &lt;actionName> -Prefix &lt;ipv6_addr|*> [-mappedRule &lt;expression>] [-excludeRule &lt;expression>]


##Arguments

<b>actionName</b>
Name of the dns64 action.

<b>Prefix</b>
The dns64 prefix to be used if the after evaluating the rules

<b>mappedRule</b>
The expression to select the criteria for ipv4 addresses to be used for synthesis.
                      Only if the mappedrule is evaluated to true the corresponding ipv4 address is used for synthesis using respective prefix, 
                      otherwise the A RR is discarded

<b>excludeRule</b>
The expression to select the criteria for eliminating the corresponding ipv6 addresses from the response.



##Example

add dns dns64action &lt;actionName&gt; -prefix f23d:f43e::0/32 [-mappedRule &lt;expr&gt;] [-excludeRule &lt;expr&gt;]

##rm dns action64

Removes a dns64 Action.


##Synopsys

rm dns action64 &lt;actionName>


##Arguments

<b>actionName</b>
Name of the dns64 action.



##Example

rm dns dns64action action1

##set dns action64

Set a DNS64 Action


##Synopsys

set dns action64 &lt;actionName> [-Prefix &lt;ipv6_addr|*>] [-mappedRule &lt;expression>] [-excludeRule &lt;expression>]


##Arguments

<b>actionName</b>
Name of the dns64 action.

<b>Prefix</b>
The dns64 prefix to be used if the after evaluating the rules

<b>mappedRule</b>
The expression to select the criteria for ipv4 addresses to be used for synthesis.
                      Only if the mappedrule is evaluated to true the corresponding ipv4 address is used for synthesis using respective prefix, 
                      otherwise the A RR is discarded

<b>excludeRule</b>
The expression to select the criteria for eliminating the corresponding ipv6 addresses from the response.



##Example

set dns dns64action -prefix -mappedrule -excluderule

##unset dns action64

Use this command to remove dns action64 settings.Refer to the set dns action64 command for meanings of the arguments.


##Synopsys

unset dns action64 &lt;actionName> [-Prefix] [-mappedRule] [-excludeRule]


##show dns action64

Used to display the action-related information.


##Synopsys

show dns action64 [&lt;actionName>]


##Arguments

<b>actionName</b>
Name of the dns64 action.

<b>format</b>

<b>level</b>



##Outputs

<b>Prefix</b>
The dns64 prefix to be used if the after evaluating the rules

<b>mappedRule</b>
The expression to select the criteria for ipv4 addresses to be used for synthesis.
                      Only if the mappedrule is evaluated to true the corresponding ipv4 address is used for synthesis using respective prefix, 
                      otherwise the A RR is discarded

<b>excludeRule</b>
The expression to select the criteria for eliminating the corresponding ipv6 addresses from the response.

<b>builtin</b>
Flag to determine whether dna64action is default or not

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show dns dns64action

