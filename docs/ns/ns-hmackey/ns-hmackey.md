#ns hmacKey

The following operations can be performed on "ns hmacKey":


[add](#add-ns-hmackey) | [set](#set-ns-hmackey) | [unset](#unset-ns-hmackey) | [rm](#rm-ns-hmackey) | [show](#show-ns-hmackey)

##add ns hmacKey

Create a key to be used in HMAC() policy functions.


##Synopsys

add ns hmacKey &lt;name> -digest &lt;digest> [-keyValue ] [-comment &lt;string>]


##Arguments

<b>name</b>
Key name.  This follows the same syntax rules as other default syntax expression entity names:
   It must begin with an alpha character (A-Z or a-z) or an underscore (_).
   The rest of the characters must be alpha, numeric (0-9) or underscores.
   It cannot be re or xp (reserved for regular and XPath expressions).
   It cannot be a default syntax expression reserved word (e.g. SYS or HTTP).
   It cannot be used for an existing default syntax expression object (HTTP callout, patset, dataset, stringmap, or named expression).

<b>digest</b>
Digest (hash) function to be used in the HMAC computation.
Possible values: MD2, MD4, MD5, SHA1, SHA224, SHA256, SHA384, SHA512

<b>keyValue</b>
The hex-encoded key to be used in the HMAC computation. The key can be any length (up to a NetScaler-imposed maximum of 255 bytes). If the length is less than the digest block size, it will be zero padded up to the block size. If it is greater than the block size, it will be hashed using the digest function to the block size. The block size for each digest is:
   MD2    - 16 bytes
   MD4    - 16 bytes
   MD5    - 16 bytes
   SHA1   - 20 bytes
   SHA224 - 28 bytes
   SHA256 - 32 bytes
   SHA384 - 48 bytes
   SHA512 - 64 bytes
Note that the key will be encrypted when it it is saved.

<b>comment</b>
Comments associated with this encryption key.



##Example

add ns hmacKey my_hmac_key -digest sha1 -keyValue 0c753c6c5ef859189cacdf95b506d02c1797407d

##set ns hmacKey

Change an existing HMAC key.


##Synopsys

set ns hmacKey &lt;name> [-digest &lt;digest>] [-keyValue ] [-comment &lt;string>]


##Arguments

<b>name</b>
Key name.  This follows the same syntax rules as other default syntax expression entity names:
   It must begin with an alpha character (A-Z or a-z) or an underscore (_).
   The rest of the characters must be alpha, numeric (0-9) or underscores.
   It cannot be re or xp (reserved for regular and XPath expressions).
   It cannot be a default syntax expression reserved word (e.g. SYS or HTTP).
   It cannot be used for an existing default syntax expression object (HTTP callout, patset, dataset, stringmap, or named expression).

<b>digest</b>
Digest (hash) function to be used in the HMAC computation.
Possible values: MD2, MD4, MD5, SHA1, SHA224, SHA256, SHA384, SHA512

<b>keyValue</b>
The hex-encoded key to be used in the HMAC computation. The key can be any length (up to a NetScaler-imposed maximum of 255 bytes). If the length is less than the digest block size, it will be zero padded up to the block size. If it is greater than the block size, it will be hashed using the digest function to the block size. The block size for each digest is:
   MD2    - 16 bytes
   MD4    - 16 bytes
   MD5    - 16 bytes
   SHA1   - 20 bytes
   SHA224 - 28 bytes
   SHA256 - 32 bytes
   SHA384 - 48 bytes
   SHA512 - 64 bytes
Note that the key will be encrypted when it it is saved.

<b>comment</b>
Comments associated with this encryption key.



##Example

set ns hmacKey my_hmac_key -keyValue f348c594341a840a1f641a1cf24aa24c15eb1317

##unset ns hmacKey

Use this command to remove ns hmacKey settings.Refer to the set ns hmacKey command for meanings of the arguments.


##Synopsys

unset ns hmacKey &lt;name> -comment


##rm ns hmacKey

Remove an HMACkey. There can be no existing HMAC() functions that use the key.


##Synopsys

rm ns hmacKey &lt;name>


##Arguments

<b>name</b>
Key name.  This follows the same syntax rules as other default syntax expression entity names:
   It must begin with an alpha character (A-Z or a-z) or an underscore (_).
   The rest of the characters must be alpha, numeric (0-9) or underscores.
   It cannot be re or xp (reserved for regular and XPath expressions).
   It cannot be a default syntax expression reserved word (e.g. SYS or HTTP).
   It cannot be used for an existing default syntax expression object (HTTP callout, patset, dataset, stringmap, or named expression).



##Example

rm ns hmacKey my_hmac_key

##show ns hmacKey

Display configured HMAC keys


##Synopsys

show ns hmacKey [&lt;name>]


##Arguments

<b>name</b>
Key name.  This follows the same syntax rules as other default syntax expression entity names:
   It must begin with an alpha character (A-Z or a-z) or an underscore (_).
   The rest of the characters must be alpha, numeric (0-9) or underscores.
   It cannot be re or xp (reserved for regular and XPath expressions).
   It cannot be a default syntax expression reserved word (e.g. SYS or HTTP).
   It cannot be used for an existing default syntax expression object (HTTP callout, patset, dataset, stringmap, or named expression).



##Outputs

<b>digest</b>
Digest (hash) function to be used in the HMAC computation.

<b>keyValue</b>
The hex-encoded key to be used in the HMAC computation. The key can be any length (up to a NetScaler-imposed maximum of 255 bytes). If the length is less than the digest block size, it will be zero padded up to the block size. If it is greater than the block size, it will be hashed using the digest function to the block size. The block size for each digest is:
   MD2    - 16 bytes
   MD4    - 16 bytes
   MD5    - 16 bytes
   SHA1   - 20 bytes
   SHA224 - 28 bytes
   SHA256 - 32 bytes
   SHA384 - 48 bytes
   SHA512 - 64 bytes
Note that the key will be encrypted when it it is saved.

<b>comment</b>
Comments associated with this encryption key.

<b>stateflag</b>

<b>devno</b>

<b>count</b>



