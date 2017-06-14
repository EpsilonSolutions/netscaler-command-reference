#ssl rsakey

The following operations can be performed on "ssl rsakey":


##create ssl rsakey

Generates an RSA key.


##Synopsys

create ssl rsakey &lt;keyFile> &lt;bits> [-exponent ( 3 | F4 )] [-keyform ( DER | PEM )] [-des | -des3] {-password }


##Arguments

<b>keyFile</b>
Name for and, optionally, path to the RSA key file. /nsconfig/ssl/ is the default path.
Maximum value: 63

<b>bits</b>
Size, in bits, of the RSA key.
Minimum value: 512
Maximum value: 4096

<b>exponent</b>
Public exponent for the RSA key. The exponent is part of the cipher algorithm and is required for creating the RSA key.
Possible values: 3, F4
Default value: FIPSEXP_F4

<b>keyform</b>
Format in which the RSA key file is stored on the appliance.
Possible values: DER, PEM
Default value: FORMAT_PEM

<b>des</b>
Encrypt the generated RSA key by using the DES algorithm. On the command line, you are prompted to enter the pass phrase (password) that is used to encrypt the key.

<b>des3</b>
Encrypt the generated RSA key by using the Triple-DES algorithm. On the command line, you are prompted to enter the pass phrase (password) that is used to encrypt the key.

<b>password</b>
Pass phrase to use for encryption if DES or DES3 option is selected.
Maximum value: 31



##Example

create ssl rsakey /nsconfig/ssl/rsa1024.pem 1024 -exp F4

##Related Commands

<ul><li><a href="../../../-ssl/-ssl">create ssl cert</a></li><li><a href="../../../ate-ssl-ce/ate-ssl-ce">create ssl certreq</a></li><li><a href="../../../-ssl-ce/-ssl-ce">add ssl certkey</a></li></ul>



