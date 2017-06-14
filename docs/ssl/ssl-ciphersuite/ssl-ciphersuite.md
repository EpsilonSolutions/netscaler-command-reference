#ssl ciphersuite

The following operations can be performed on "ssl ciphersuite":


##show ssl ciphersuite

Displays information about all the cipher suites configured on the appliance, or displays detailed information about the specified cipher-suite.  A cipher suite comprises a protocol and the following algorithms:  key exchange (Kx), authentication (Au), encryption (Enc), and message authentication code (Mac).


##Synopsys

show ssl ciphersuite [&lt;cipherName>]


##Arguments

<b>cipherName</b>
Name of the cipher suite for which to show detailed information.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>description</b>
Cipher suite description.

<b>flag</b>

<b>stateflag</b>

<b>devno</b>

<b>count</b>



##Example

1) An example of the output of the show ssl cipher SSL3-RC4-MD5 command is as follows:Cipher Name: SSL3-RC4-MD5Description: SSLv3 Kx=RSA      Au=RSA  Enc=RC4(128)  Mac=MD52) This example displays the details of individual ciphers in the system predefinedcipher-alias: SSLv2 (the command show ssl cipher SSLv2 has been entered):8 configured cipher(s)in alias1) Cipher Name: SSL2-RC4-MD5   Description: SSLv2 Kx=RSA      Au=RSA  Enc=RC4(128)  Mac=MD52) Cipher Name: SSL2-EXP-RC4-MD5   Description: SSLv2 Kx=RSA(512) Au=RSA  Enc=RC4(40)   Mac=MD5 export3) Cipher Name: SSL2-RC2-CBC-MD5   Description: SSLv2 Kx=RSA      Au=RSA  Enc=RC2(128)  Mac=MD54) Cipher Name: SSL2-EXP-RC2-CBC-MD5   Description: SSLv2 Kx=RSA(512) Au=RSA  Enc=RC2(40)   Mac=MD5 export5) Cipher Name: SSL2-DES-CBC-MD5   Description: SSLv2 Kx=RSA      Au=RSA  Enc=DES(56)   Mac=MD56) Cipher Name: SSL2-DES-CBC3-MD5   Description: SSLv2 Kx=RSA      Au=RSA  Enc=3DES(168) Mac=MD57) Cipher Name: SSL2-RC4-64-MD5   Description: SSLv2 Kx=RSA      Au=RSA  Enc=RC4(64)   Mac=MD5

