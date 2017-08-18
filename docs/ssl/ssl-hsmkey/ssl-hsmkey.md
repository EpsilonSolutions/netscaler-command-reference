#ssl hsmKey

The following operations can be performed on "ssl hsmKey":


[add](#add-ssl-hsmkey) | [rm](#rm-ssl-hsmkey) | [show](#show-ssl-hsmkey)

##add ssl hsmKey

Add HSM Key.


##Synopsys

add ssl hsmKey &lt;hsmKeyName> [-hsmType ( THALES | SAFENET )] [-key &lt;string> | -serialNum &lt;string>] {-password }


##Arguments

<b>hsmKeyName</b>

<b>hsmType</b>
Type of HSM.
Possible values: THALES, SAFENET
Default value: THALES

<b>key</b>
Name of and, optionally, path to the HSM key file. /var/opt/nfast/kmdata/local/ is the default path. Applies only to THALES HSM.
Maximum value: 63

<b>serialNum</b>
Serial number of the partition on which the key is present. Applies only to SafeNet HSM.
Maximum value: 16

<b>password</b>
Password for a partition. Applies only to SafeNet HSM.



##Example

add ssl hsmkey rsa1 key_simple_rsa1

##rm ssl hsmKey

Removes the specified HSM key, from the HSM Appliance.


##Synopsys

rm ssl hsmKey &lt;hsmKeyName> [-hsmType ( THALES | SAFENET )] [-serialNum &lt;string>] {-password }


##Arguments

<b>hsmKeyName</b>
Name of the HSMKEY.

<b>hsmType</b>
Type of the HSMKEY.
Possible values: THALES, SAFENET
Default value: THALES

<b>serialNum</b>
SerialNum of a partition on which Safent HSMKey is present.
Maximum value: 16

<b>password</b>
Password of a partition on which SafeNet HSMkey is present.



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

<b>hsmType</b>
Type of the HSM key.

<b>serialNum</b>
SerialNum of a partition on which Safenet key is present.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

An example of output of 'show ssl hsmkey' command is as shown below:sh ssl hsmkey	1 SSL HSM key:1)	SSL HSM Key Name: key_simple_rsa1

