#ssl dsaKey

The following operations can be performed on "ssl dsaKey":


##create ssl dsaKey

Generates a DSA key.


##Synopsys

create ssl dsaKey &lt;keyFile> &lt;bits> [-keyform ( DER | PEM )] [-des | -des3] {-password }


##Arguments

<b>keyFile</b>
Name for and, optionally, path to the DSA key file. /nsconfig/ssl/ is the default path.
Maximum value: 63

<b>bits</b>
Size, in bits, of the DSA key.
Minimum value: 512
Maximum value: 2048

<b>keyform</b>
Format in which the DSA key file is stored on the appliance.
Possible values: DER, PEM
Default value: FORMAT_PEM

<b>des</b>
Encrypt the generated DSA key by using the DES algorithm. On the command line, you are prompted to enter the pass phrase (password) that will be used to encrypt the key.

<b>des3</b>
Encrypt the generated DSA key by using the Triple-DES algorithm. On the command line, you are prompted to enter the pass phrase (password) that will be used to encrypt the key.

<b>password</b>
Pass phrase to use for encryption if DES or DES3 option is selected.
Maximum value: 31



##Example

create ssl dsakey /nsconfig/ssl/dsa1024.pem 1024

##Related Commands

<ul><li><a href="../../../-ssl/-ssl">create ssl cert</a></li><li><a href="../../../ate-ssl-ce/ate-ssl-ce">create ssl certreq</a></li><li><a href="../../../-ssl-ce/-ssl-ce">add ssl certkey</a></li></ul>



