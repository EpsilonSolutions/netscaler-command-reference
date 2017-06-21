#dns suffix

The following operations can be performed on "dns suffix":


[add](#add-dns-suffix) | [rm](#rm-dns-suffix) | [show](#show-dns-suffix)

##add dns suffix

Specifies a suffix that can be used to complete domain names that are not fully qualified. For example, if you specify the example.com suffix, and the NetScaler appliance is required to resolve the incomplete domain name "myhost," it attempts to resolve "myhost.example.com."


##Synopsys

add dns suffix &lt;dnsSuffix>


##Arguments

<b>dnsSuffix</b>
Suffix to be appended when resolving domain names that are not fully qualified.



##Example

add dns suffix netscaler.comIf the incoming domain name "engineering" is not resolved by itself, the system will append the suffix netscaler.com and attempt to resolve the name engineering.netscaler.com.

##rm dns suffix

Removes a DNS suffix.


##Synopsys

rm dns suffix &lt;dnsSuffix>


##Arguments

<b>dnsSuffix</b>
DNS suffix to remove.



##show dns suffix

Displays the specified DNS suffix or, if no DNS suffix is specified, all configured DNS suffixes.


##Synopsys

show dns suffix [&lt;dnsSuffix>]


##Arguments

<b>dnsSuffix</b>
DNS suffix to display.



##Outputs

<b>devno</b>

<b>count</b>

<b>stateflag</b>



