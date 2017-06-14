#ns encryptionParams

The following operations can be performed on "ns encryptionParams":


[set](#set-ns-encryptionparams) | [show](#show-ns-encryptionparams)

##set ns encryptionParams

Sets the parameters required for encrypting or decrypting content.


##Synopsys

set ns encryptionParams -method &lt;method> [-keyValue ]


##Arguments

<b>method</b>
Cipher method (and key length) to be used to encrypt and decrypt content. The default value is AES256.
Possible values: NONE, RC4, DES3, AES128, AES192, AES256

<b>keyValue</b>
The base64-encoded key generation number, method, and key value.
Note:
* Do not include this argument if you are changing the encryption method.
* To generate a new key value for the current encryption method, specify an empty string \\(""\\) as the value of this parameter. The parameter is passed implicitly, with its automatically generated value, to the NetScaler packet engines even when it is not included in the command. Passing the parameter to the packet engines enables the appliance to save the key value to the configuration file and to propagate the key value to the secondary appliance in a high availability setup.



##Example

set ns encryptionParams -method aes128

##show ns encryptionParams

Displays the encryption method configured on the NetScaler appliance.


##Synopsys

show ns encryptionParams


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>method</b>
The cipher method (and key length) used to encrypt and decrypt content.

<b>keyValue</b>
The base64-encoded key generation number, method, and key value.
Note:
* Do not include this argument if you are changing the encryption method.
* To generate a new key value for the current encryption method, specify an empty string \\(""\\) as the value of this parameter. The parameter is passed implicitly, with its automatically generated value, to the NetScaler packet engines even when it is not included in the command. Passing the parameter to the packet engines enables the appliance to save the key value to the configuration file and to propagate the key value to the secondary appliance in a high availability setup.



