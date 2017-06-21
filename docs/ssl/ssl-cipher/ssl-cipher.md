#ssl cipher

The following operations can be performed on "ssl cipher":


[add](#add-ssl-cipher) | [bind](#bind-ssl-cipher) | [show](#show-ssl-cipher) | [rm](#rm-ssl-cipher) | [unbind](#unbind-ssl-cipher)

##add ssl cipher

Creates a user-defined cipher group, which you can bind to an SSL virtual server instead of binding ciphers individually. Although you cannot modify a built-in cipher group, you can add built-in cipher groups as well as individual ciphers to a user-defined cipher group.


##Synopsys

add ssl cipher &lt;cipherGroupName>


##Arguments

<b>cipherGroupName</b>
Name for the user-defined cipher group. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the cipher group is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my ciphergroup" or 'my ciphergroup').



##Example

1)	add ssl cipher mygroup SSL2-RC4-MD5 SSL2-EXP-RC4-MD5	The above command creates a new cipher-group by the name: mygroup, with the two ciphers SSL2-RC4-MD5 and SSL2-EXP-RC4-MD5, as part of the cipher-group.If a cipher-group by the name: mygroup already exists in system, then the two ciphers is added to the list of ciphers contained in the group.2)	add ssl cipher mygroup HIGH MEDIUM	The above command creates a new cipher-group by the name: mygroup, with the ciphers from the cipher alias "HIGH" and "MEDIUM" as part of the cipher group.If a cipher-group by the name, mygroup, already exists in system, then the ciphers from the two aliases is added to the list of ciphers contained in the group.

##bind ssl cipher

Adds ciphers to a user-defined cipher group. You can add an existing cipher group to a user-defined cipher group but you cannot modify a built-in cipher group.


##Synopsys

bind ssl cipher [&lt;cipherGroupName>@] [-cipherName &lt;string>]


##Arguments

<b>cipherGroupName</b>
Name of the user-defined cipher group.

<b>cipherName</b>
Name of the individual cipher, user-defined cipher group, or predefined (built-in) cipher alias to add to the cipher group.



##Example

1)	bind ssl cipher sslvip ADD SSL3-RC4-SHAThe above example appends the cipher SSL3-RC4-SHA to the cipher-suite already configured for the SSL virtual server sslvip.2)	bind ssl cipher sslvip REM NULLThe above example removes the ciphers identified by the system's predefined cipher-alias -NULL from the cipher-suite already configured for the SSL virtual server sslvip.3)	bind ssl cipher sslvip ORD HIGHThe above example overrides the existing cipher-suite configured for the SSL virtual server with ciphers, having HIGH encryption strength (ciphers supporting 168-bit encryption).Note: The individual ciphers contained in a system predefined cipher-alias can beviewed by using the following command: show ssl cipher &lt;cipherAlaisName&gt;

##Related Commands

<ul><li><a href="../../../w-ssl-vs/w-ssl-vs">show ssl vserver</a></li></ul>



##show ssl cipher

Displays information about all the cipher groups defined on the appliance, or displays detailed information about the specified cipher group.


##Synopsys

show ssl cipher [&lt;cipherGroupName>]


##Arguments

<b>cipherGroupName</b>
Name of the cipher group for which to show detailed information.



##Outputs

<b>description</b>
Cipher suite description.

<b>cipherName</b>
Cipher name.

<b>flag</b>

<b>stateflag</b>

<b>peFlags</b>

<b>devno</b>

<b>count</b>



##Example

1) An example of the output of the show ssl cipher SSL3-RC4-MD5 command is as follows:Cipher Name: SSL3-RC4-MD5Description: SSLv3 Kx=RSA      Au=RSA  Enc=RC4(128)  Mac=MD52) This example displays the details of individual ciphers in the system predefinedcipher-alias: SSLv2 (the command show ssl cipher SSLv2 has been entered):8 configured cipher(s)in alias1) Cipher Name: SSL2-RC4-MD5   Description: SSLv2 Kx=RSA      Au=RSA  Enc=RC4(128)  Mac=MD52) Cipher Name: SSL2-EXP-RC4-MD5   Description: SSLv2 Kx=RSA(512) Au=RSA  Enc=RC4(40)   Mac=MD5 export3) Cipher Name: SSL2-RC2-CBC-MD5   Description: SSLv2 Kx=RSA      Au=RSA  Enc=RC2(128)  Mac=MD54) Cipher Name: SSL2-EXP-RC2-CBC-MD5   Description: SSLv2 Kx=RSA(512) Au=RSA  Enc=RC2(40)   Mac=MD5 export5) Cipher Name: SSL2-DES-CBC-MD5   Description: SSLv2 Kx=RSA      Au=RSA  Enc=DES(56)   Mac=MD56) Cipher Name: SSL2-DES-CBC3-MD5   Description: SSLv2 Kx=RSA      Au=RSA  Enc=3DES(168) Mac=MD57) Cipher Name: SSL2-RC4-64-MD5   Description: SSLv2 Kx=RSA      Au=RSA  Enc=RC4(64)   Mac=MD5

##rm ssl cipher

Removes a user-defined cipher group from the appliance.


##Synopsys

rm ssl cipher &lt;cipherGroupName>


##Arguments

<b>cipherGroupName</b>
Name of the user-defined cipher group to remove.



##Example

1)	rm ssl cipher mygroup SSL2-RC4-MD5The above example removes the cipher SSL2-RC4-MD5 from the cipher group mygroup.2)	rm ssl cipher mygroupThe above example will remove the cipher group 'mygroup' from the system.

##unbind ssl cipher

Removes all the ciphers from a user-defined cipher group. You can only remove individual ciphers from a user-defined cipher group. Removing groups is not supported.


##Synopsys

unbind ssl cipher &lt;cipherGroupName> [-cipherName &lt;string> ...]


##Arguments

<b>cipherGroupName</b>
Name of the user-defined cipher group.

<b>cipherName</b>
Name(s) of the cipher(s) to be removed from the user-defined cipher group.



##Example

1)	rm ssl cipher mygroup SSL2-RC4-MD5The above example removes the cipher SSL2-RC4-MD5 from the cipher group mygroup.2)	rm ssl cipher mygroupThe above example will remove the cipher group 'mygroup' from the system.

