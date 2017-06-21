#ssl hsmKey

The following operations can be performed on "ssl hsmKey":


[add](#add-ssl-hsmkey) | [rm](#rm-ssl-hsmkey) | [show](#show-ssl-hsmkey)

##add ssl hsmKey

Add HSM Key.


##Synopsys

add ssl hsmKey &lt;hsmKeyName> -key &lt;string>


##Arguments

<b>hsmKeyName</b>

<b>key</b>
Name of and, optionally, path to the HSM key file. /var/opt/nfast/kmdata/local/ is the default path
Maximum value: 63



##Example

add ssl hsmkey rsa1 key_simple_rsa1

##rm ssl hsmKey

Removes the specified HSM key, from the HSM Appliance.


##Synopsys

rm ssl hsmKey &lt;hsmKeyName>


##Arguments

<b>hsmKeyName</b>
Name of the HSMKEY to be removed



##Example

rm hsmkey key_simple_rsa1

##show ssl hsmKey

Displays lists of all the HSM Keys Added on the NetScaler appliance.


##Synopsys

show ssl hsmKey [&lt;hsmKeyName>]


##Arguments

<b>hsmKeyName</b>
Name of the HSM Key for which to show detailed information.



##Outputs

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

An example of output of 'show ssl hsmkey' command is as shown below:sh ssl hsmkey	1 SSL HSM key:1)	SSL HSM Key Name: key_simple_rsa1

