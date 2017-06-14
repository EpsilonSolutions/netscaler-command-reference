#ssl wrapkey

The following operations can be performed on "ssl wrapkey":


[create](#create-ssl-wrapkey) | [rm](#rm-ssl-wrapkey) | [show](#show-ssl-wrapkey)

##create ssl wrapkey

Generates a wrap key.


##Synopsys

create ssl wrapkey &lt;wrapKeyName> {-password } {-salt }


##Arguments

<b>wrapKeyName</b>
Name for the wrap key. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the wrap key is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my key" or 'my key').

<b>password</b>
Password string for the wrap key.

<b>salt</b>
Salt string for the wrap key.



##Example

create wrapkey wrap1 -password wrapkey123 -salt wrapsalt123

##rm ssl wrapkey

Removes all the wrap keys, or the specified wrap key, from the appliance.


##Synopsys

rm ssl wrapkey &lt;wrapKeyName> ...


##Arguments

<b>wrapKeyName</b>
Name of the wrap key to remove.



##Example

rm wrapkey wrap1

##show ssl wrapkey

Display the wrap keys.


##Synopsys

show ssl wrapkey


##Arguments

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>wrapKeyName</b>
Wrap key name.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

An example of output of 'show wrapkey' command is as shown below:sh wrapkey	1 WRAP key:1)	WRAP Key Name: wrap1

