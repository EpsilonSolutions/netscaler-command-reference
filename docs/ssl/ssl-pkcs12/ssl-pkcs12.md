#ssl pkcs12

The following operations can be performed on "ssl pkcs12":


##convert ssl pkcs12

Converts the end-user certificate from PEM encoding format to PKCS#12 format. This certificate can then be distributed and installed in browsers as client certificates.


##Synopsys

convert ssl pkcs12 &lt;outfile> [-import  [-pkcs12File &lt;input_filename>]  [-des | -des3] ] [-export  [-certFile &lt;input_filename>]  [-keyFile &lt;input_filename>]] {-password } {-PEMPassPhrase }


##Arguments

<b>outfile</b>
Name for and, optionally, path to, the output file that contains the certificate and the private key after converting from PKCS#12 to PEM format. /nsconfig/ssl/ is the default path.
If importing, the certificate-key pair is stored in PEM format. If exporting, the certificate-key pair is stored in PKCS#12 format.
Maximum value: 63

<b>import</b>
Convert the certificate and private-key from PKCS#12 format to PEM format.

<b>export</b>
Convert the certificate and private key from PEM format to PKCS#12 format. On the command line, you are prompted to enter the pass phrase.

<b>password</b>

<b>PEMPassPhrase</b>



##Example

1)	convert  ssl pkcs12   /nsconfig/ssl/client_certkey.p12 -export -cert /nsconfig/ssl/client_certcert.pem  -key /nsconfig/ssl/client_key.pemThe above example CLI command converts the PEM encoded certificate and key file to PKCS#12.2)	convert ssl  pkcs12 /nsconfig/ssl/client_certkey.pem -import -pkcs12 /nsconfig/ssl/client_certcertkey.p12The above example CLI command converts the PKCS12 file to PEM format.3)	convert ssl  pkcs12   /nsconfig/ssl/client_certkey.pem -import -pkcs12 /nsconfig/ssl/client_certcertkey.p12  -desThe above example CLI command converts the PKCS12 file to PEM format, with encrypted key.Note:	The -des option will encrypt the output key using DES algorithm. User will be prompted to enter the pass-phrase to be used for encryption.

##Related Commands

<ul><li><a href="../../../te-ssl-r/te-ssl-r">create ssl rsakey</a></li><li><a href="../../../te-ssl-d/te-ssl-d">create ssl dsakey</a></li><li><a href="../../../ate-ssl-ce/ate-ssl-ce">create ssl certreq</a></li><li><a href="../../../-ssl/-ssl">create ssl cert</a></li></ul>



