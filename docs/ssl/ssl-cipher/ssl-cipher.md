#ssl cipher

The following operations can be performed on "ssl cipher":


[add](#add-ssl-cipher) | [bind](#bind-ssl-cipher) | [set](#set-ssl-cipher) | [unset](#unset-ssl-cipher) | [show](#show-ssl-cipher) | [rm](#rm-ssl-cipher) | [unbind](#unbind-ssl-cipher)

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

1) add ssl cipher mygroup SSL2-RC4-MD5 SSL2-EXP-RC4-MD5     The above command creates a new cipher-group by the name: mygroup, with the two ciphers SSL2-RC4-MD5 and SSL2-EXP-RC4-MD5, as part of the cipher-group.If a cipher-group by the name: mygroup already exists in system, then the two ciphers is added to the list of ciphers contained in the group.2)   add ssl cipher mygroup HIGH MEDIUM     The above command creates a new cipher-group by the name: mygroup, with the ciphers from the cipher alias "HIGH" and "MEDIUM" as part of the cipher group.If a cipher-group by the name, mygroup, already exists in system, then the ciphers from the two aliases is added to the list of ciphers contained in the group.3)   add ssl cipher cipher_sha     The above command creates a new cipher-group by the name: cipher_sha and No ciphers added to the created cipher group.

##bind ssl cipher

Adds ciphers to a user-defined cipher group. You can add an existing cipher group to a user-defined cipher group but you cannot modify a built-in cipher group.


##Synopsys

bind ssl cipher [&lt;cipherGroupName>@  [-cipherPriority &lt;positive_integer>]] [-cipherName &lt;string>]


##Arguments

<b>cipherGroupName</b>
Name of the user-defined cipher group.

<b>cipherName</b>
Name of the individual cipher, user-defined cipher group, or predefined (built-in) cipher alias to add to the cipher group.

<b>cipherPriority</b>
Priority of the cipher to be added
Minimum value: 1
Maximum value: 1000



##Example

1) bind ssl cipher sslvip ADD SSL3-RC4-SHAThe above example appends the cipher SSL3-RC4-SHA to the cipher-suite already configured for the SSL virtual server sslvip.2)  bind ssl cipher sslvip REM NULLThe above example removes the ciphers identified by the system's predefined cipher-alias -NULL from the cipher-suite already configured for the SSL virtual server sslvip.3)  bind ssl cipher sslvip ORD HIGHThe above example overrides the existing cipher-suite configured for the SSL virtual server with ciphers, having HIGH encryption strength (ciphers supporting 168-bit encryption).4)  bind ssl cipher cipher_sha -cipherName TLS1.2-AES-128-SHA256The above example adds the cipher TLS1.2-AES-128-SHA256 to the cipher group cipher_sha. Priority of added cipersuite will be next available maximum value in cipher group cipher_sha.3i)  bind ssl cipher cipher_sha -cipherName TLS1.2-AES-128-SHA256 -cipherPriority 5The above example adds the cipher TLS1.2-AES-128-SHA256 to the cipher group cipher_sha at priority 5. If cipher already bounded at higher priority in the cipher group, then cipher priority remains same.Note: The individual ciphers contained in a system predefined cipher-alias can beviewed by using the following command: show ssl cipher &lt;cipherAlaisName&gt;

##Related Commands

<ul><li><a href="../../../w-ssl-vs/w-ssl-vs">show ssl vserver</a></li></ul>



##set ssl cipher

Modifies the priority of the cipher within a cipher group.


##Synopsys

set ssl cipher &lt;cipherGroupName> (-cipherName &lt;string>  -cipherPriority &lt;positive_integer>)


##Arguments

<b>cipherGroupName</b>
Name of the cipher group.

<b>cipherName</b>
Cipher name.

<b>cipherPriority</b>
This indicates priority assigned to the particular cipher
Minimum value: 1



##Example

1) set ssl cipher cipher_sha -cipher TLS1-AES-128-CBC-SHA -cipherpriority 1The above example sets the priority of TLS1-AES-128-CBC-SHA to 1 within the cipher group cipher_sha.

##unset ssl cipher

Use this command to remove ssl cipher settings.Refer to the set ssl cipher command for meanings of the arguments.


##Synopsys

unset ssl cipher &lt;cipherGroupName> -cipherName -cipherPriority


##show ssl cipher

Displays information about all the cipher groups defined on the appliance, or displays detailed information about the specified cipher group.


##Synopsys

show ssl cipher [&lt;cipherGroupName>] [-sslProfile &lt;string>]


##Arguments

<b>cipherGroupName</b>
Name of the cipher group for which to show detailed information.

<b>sslProfile</b>
Name of the profile to which cipher is attached.



##Outputs

<b>description</b>
Cipher suite description.

<b>cipherName</b>
Cipher name.

<b>flag</b>

<b>stateflag</b>

<b>cipherPriority</b>
This indicates priority assigned to the particular cipher

<b>peFlags</b>

<b>devno</b>

<b>count</b>



##Example

1) An example of the output of the show ssl cipher SSL3-RC4-MD5 command is as follows:        Cipher Name: SSL3-RC4-MD5        Description: SSLv3 Kx=RSA      Au=RSA  Enc=RC4(128)  Mac=MD52) This example displays the details of individual ciphers in the system predefinedcipher-alias: SSLv3 (the command show ssl cipher SSLv3 has been entered):1)      Cipher Name: SSL3-RC4-MD5    Priority:1        Description: SSLv3 Kx=RSA      Au=RSA  Enc=RC4(128)  Mac=MD52)      Cipher Name: SSL3-RC4-SHA    Priority:2        Description: SSLv3 Kx=RSA      Au=RSA  Enc=RC4(128)  Mac=SHA13)      Cipher Name: SSL3-DES-CBC3-SHA    Priority:3        Description: SSLv3 Kx=RSA      Au=RSA  Enc=3DES(168) Mac=SHA14)      Cipher Name: SSL3-DES-CBC-SHA    Priority:4        Description: SSLv3 Kx=RSA      Au=RSA  Enc=DES(56)   Mac=SHA15)      Cipher Name: TLS1-AES-256-CBC-SHA    Priority:5        Description: SSLv3 Kx=RSA      Au=RSA  Enc=AES(256)  Mac=SHA16)      Cipher Name: TLS1-AES-128-CBC-SHA    Priority:6        Description: SSLv3 Kx=RSA      Au=RSA  Enc=AES(128)  Mac=SHA17)      Cipher Name: SSL3-EXP-RC4-MD5    Priority:7        Description: SSLv3 Kx=RSA(512) Au=RSA  Enc=RC4(40)   Mac=MD5  Export8)      Cipher Name: SSL3-EXP-DES-CBC-SHA    Priority:8        Description: SSLv3 Kx=RSA(512) Au=RSA  Enc=DES(40)   Mac=SHA1 Export9)      Cipher Name: SSL3-EXP-RC2-CBC-MD5    Priority:9        Description: SSLv3 Kx=RSA(512) Au=RSA  Enc=RC2(40)   Mac=MD5  Export10)     Cipher Name: SSL3-EDH-DSS-DES-CBC3-SHA    Priority:10        Description: SSLv3 Kx=DH       Au=DSS  Enc=3DES(168) Mac=SHA1

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

1) rm ssl cipher mygroup SSL2-RC4-MD5The above example removes the cipher SSL2-RC4-MD5 from the cipher group mygroup.2)  rm ssl cipher mygroupThe above example will remove the cipher group 'mygroup' from the system.3)  unbind ssl cipher cipher_sha -cipherName TLS1.2-AES-256-SHA256The above example will remove the cipher TLS1.2-AES-256-SHA256 from cipher_sha cipher group.

