#dns key

The following operations can be performed on "dns key":


[add](#add-dns-key) | [create](#create-dns-key) | [set](#set-dns-key) | [unset](#unset-dns-key) | [rm](#rm-dns-key) | [show](#show-dns-key)

##add dns key

Adds a DNS key to the zone that is specified in the key file.


##Synopsys

add dns key &lt;keyName> &lt;publickey> &lt;privatekey> [-expires &lt;positive_integer>  [&lt;units>]] [-notificationPeriod &lt;positive_integer>  [&lt;units>]] [-TTL &lt;secs>]


##Arguments

<b>keyName</b>
Name of the public-private key pair to publish in the zone.

<b>publickey</b>
File name of the public key.

<b>privatekey</b>
File name of the private key.

<b>expires</b>
Time period for which to consider the key valid, after the key is used to sign a zone.
Default value: 120
Minimum value: 1
Maximum value: 32767

<b>units</b>
Units for the notification period.
Possible values: MINUTES, HOURS, DAYS
Default value: DAYS

<b>notificationPeriod</b>
Time at which to generate notification of key expiration, specified as number of days, hours, or minutes before expiry. Must be less than the expiry period. The notification is an SNMP trap sent to an SNMP manager. To enable the appliance to send the trap, enable the DNSKEY-EXPIRY SNMP alarm.
Default value: 7
Minimum value: 1
Maximum value: 32767

<b>TTL</b>
Time to Live (TTL), in seconds, for the DNSKEY resource record created in the zone. TTL is the time for which the record must be cached by the DNS proxies. If the TTL is not specified, either the DNS zone's minimum TTL or the default value of 3600 is used.
Default value: 3600
Maximum value: 2147483647



##Example

add dns key secure.example.zsk  -public secure.example-rsasha1-1024.key-private /nsconfig/dns/secure.example-rsasha1-1024.private

##create dns key

Creates a public-private key pair to use for signing a DNS zone. The keys are created in the /nsconfig/dns/ directory on the NetScaler appliance. The private, pubic, and DS key files are created with names having the format &lt;prefix>.&lt;key/private/ds>.


##Synopsys

create dns key -zoneName &lt;string> -keyType &lt;keyType> -algorithm RSASHA1 -keySize &lt;positive_integer> -fileNamePrefix &lt;string>


##Arguments

<b>zoneName</b>
Name of the zone for which to create a key.

<b>keyType</b>
Type of key to create.
Possible values: KSK, KeySigningKey, ZSK, ZoneSigningKey
Default value: NS_DNSKEY_ZSK

<b>algorithm</b>
Algorithm to generate for zone signing.
Possible values: RSASHA1
Default value: NS_DNSKEYALGO_RSASHA1

<b>keySize</b>
Size of the key, in bits.
Default value: 512
Minimum value: 0

<b>fileNamePrefix</b>
Common prefix for the names of the generated public and private key files and the Delegation Signer (DS) resource record. During key generation, the .key, .private, and .ds suffixes are appended automatically to the file name prefix to produce the names of the public key, the private key, and the DS record, respectively.



##Example

create dns key -zone dnssec.bar -algorithm RSASHA1 -keySize 1024

##set dns key

Modifies the specified parameters of a DNS key. Note: If you change the expiry time period of a key, the NetScaler appliance, using the modified key, automatically re-signs all the resource records in the zone, provided that the zone is currently signed with the particular key.


##Synopsys

set dns key &lt;keyName> [-expires &lt;positive_integer>  [&lt;units>]] [-notificationPeriod &lt;positive_integer>  [&lt;units>]] [-TTL &lt;secs>]


##Arguments

<b>keyName</b>
Name of the public-private key pair.

<b>expires</b>
Time period for which to consider the key valid, after the key is used to sign a zone.
Default value: 120
Minimum value: 1
Maximum value: 32767

<b>units</b>
Units for the notification period.
Possible values: MINUTES, HOURS, DAYS
Default value: DAYS

<b>notificationPeriod</b>
Time at which to generate notification of key expiration, specified as number of days, hours, or minutes before expiry. Must be less than the expiry period. The notification is an SNMP trap sent to an SNMP manager. To enable the appliance to send the trap, enable the DNSKEY-EXPIRY SNMP alarm.
Default value: 7
Minimum value: 1
Maximum value: 32767

<b>TTL</b>
Time to Live (TTL), in seconds, for the DNSKEY resource record created in the zone. TTL is the time for which the record must be cached by the DNS proxies. If the TTL is not specified, either the DNS zone's minimum TTL or the default value of 3600 is used.
Default value: 3600
Maximum value: 2147483647



##Example

add dns key secure.example.zsk  -public secure.example-rsasha1-1024.key-private /nsconfig/dns/secure.example-rsasha1-1024.private

##unset dns key

Use this command to remove dns key settings.Refer to the set dns key command for meanings of the arguments.


##Synopsys

unset dns key &lt;keyName> [-expires] [-units] [-notificationPeriod] [-units] [-TTL]


##rm dns key

Removes a DNS key.


##Synopsys

rm dns key &lt;keyName>


##Arguments

<b>keyName</b>
Name of the public-private key pair.



##Example

rm dns key secure.example.zsk

##show dns key

Displays the parameters of the specified DNS key. If no DNS key name is specified, all configured DNS keys are shown. Note: You cannot view the parameters of a public/private key file. You can view the parameters of a key after you have published it in a DNS zone by using either the add dns key command or the DNS > Zones > Sign/Unsign DNS Zone dialog box.


##Synopsys

show dns key [&lt;keyName>]


##Arguments

<b>keyName</b>
Name of the public-private key pair.



##Outputs

<b>publickey</b>
File name of the public key.

<b>privatekey</b>
File name of the private key.

<b>expires</b>
Number of days since signing with this key, when the key expires.

<b>units</b>
Units for the notification period.

<b>notificationPeriod</b>
Time at which to generate notification of key expiration, specified as number of days, hours, or minutes before expiry. Must be less than the expiry period. The notification is an SNMP trap sent to an SNMP manager. To enable the appliance to send the trap, enable the DNSKEY-EXPIRY SNMP alarm.

<b>TTL</b>
Time to Live (TTL), in seconds, for the DNSKEY resource record created in the zone. TTL is the time for which the record must be cached by the DNS proxies. If the TTL is not specified, either the DNS zone's minimum TTL or the default value of 3600 is used.

<b>zoneName</b>
Name of the zone for which the key is created.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show dns key

