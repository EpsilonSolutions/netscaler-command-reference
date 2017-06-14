#ssl fipsKey

The following operations can be performed on "ssl fipsKey":


[create](#create-ssl-fipskey) | [rm](#rm-ssl-fipskey) | [show](#show-ssl-fipskey) | [import](#import-ssl-fipskey) | [export](#export-ssl-fipskey)

##create ssl fipsKey

Generates a FIPS key within the Hardware Security Module (HSM) of the FIPS card.


##Synopsys

create ssl fipsKey &lt;fipsKeyName> -modulus &lt;positive_integer> [-exponent ( 3 | F4 )]


##Arguments

<b>fipsKeyName</b>
Name for the FIPS key. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the FIPS key is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my fipskey" or 'my fipskey').

<b>modulus</b>
Modulus, in multiples of 64, of the FIPS key to be created.
Minimum value: 1024
Maximum value: 4096

<b>exponent</b>
Exponent value for the FIPS key to be created. Available values function as follows:
 3=3 (hexadecimal)
F4=10001 (hexadecimal)
Possible values: 3, F4
Default value: 3



##Example

create fipskey fips1 -modulus 1024 -exp f4

##rm ssl fipsKey

Removes all the FIPS keys, or the specified FIPS key, from the appliance.


##Synopsys

rm ssl fipsKey &lt;fipsKeyName> ...


##Arguments

<b>fipsKeyName</b>
Name of the FIPS key to remove.



##Example

rm fipskey fips1

##show ssl fipsKey

Displays information about all the FIPS keys configured on the appliance, or displays detailed information about the specified FIPS key.


##Synopsys

show ssl fipsKey [&lt;fipsKeyName>]


##Arguments

<b>fipsKeyName</b>
Name of the FIPS key for which to show detailed information.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>modulus</b>
The modulus of the key.

<b>exponent</b>
The exponent value for the key.

<b>size</b>
Size.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

1) An example of output of show ssl fipskey command is as follows:show fipskey2 FIPS keys:1)      FIPS Key Name: fips12)      FIPS Key Name: fips22) An example of output of show fipskey command with FIPS key name specified is as follows:show fipskey fips1FIPS Key Name: fips1       Modulus: 1024   Public Exponent: 3 (Hex: 0x3)

##import ssl fipsKey

Imports a FIPS key into the Hardware Security Module (HSM) of the FIPS card. Can import an existing FIPS key, or can import, as a FIPS key, an external private key, such as a key that was created on an Apache or IIS external Web server.


##Synopsys

import ssl fipsKey &lt;fipsKeyName> -key &lt;string> [-inform &lt;inform>] [-wrapKeyName &lt;string>] [-iv &lt;string>] [-exponent ( 3 | F4 )]


##Arguments

<b>fipsKeyName</b>
Name for the FIPS key to be imported. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the FIPS key is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my fipskey" or 'my fipskey').

<b>key</b>
Name of and, optionally, path to the key file to be imported.
 /nsconfig/ssl/ is the default path.

<b>inform</b>
Input format of the key file. Available formats are:
SIM - Secure Information Management; select when importing a FIPS key. If the external FIPS key is encrypted, first decrypt it, and then import it.
PEM - Privacy Enhanced Mail; select when importing a non-FIPS key.
Possible values: SIM, DER, PEM
Default value: FORMAT_SIM

<b>wrapKeyName</b>
Name of the wrap key to use for importing the key. Required for importing a non-FIPS key.

<b>iv</b>
Initialization Vector (IV) to use for importing the key. Required for importing a non-FIPS key.

<b>exponent</b>
Exponent value for the FIPS key to be created. Available values function as follows:
 3=3 (hexadecimal)
F4=10001 (hexadecimal)
Possible values: 3, F4
Default value: 3



##Example

1)	import fipskey fips1 -key /nsconfig/ssl/fipskey.simThe above example imports a FIPS key stored in the file fipskey.sim in the system.2)	import fipskey fips2 -key /nsconfig/ssl/key.der -inform DER -wrapKeyName wrapkey1 -iv wrap123The above example imports a non-FIPS key stored in the file key.der in the system.

##export ssl fipsKey

Exports a FIPS key from one appliance to another or backs up a FIPS key in a secure manner.The exported key is secured by using a strong asymmetric key encryption method.


##Synopsys

export ssl fipsKey &lt;fipsKeyName> -key &lt;string>


##Arguments

<b>fipsKeyName</b>
Name of the FIPS key to export.

<b>key</b>
Name of and, optionally, path to the exported key file.
/nsconfig/ssl/ is the default path.



##Example

export fipskey fips1 -key /nsconfig/ssl/fips1.key

