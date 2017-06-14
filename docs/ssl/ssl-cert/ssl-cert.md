#ssl cert

The following operations can be performed on "ssl cert":


##create ssl cert

Generates a signed X509 Certificate.


##Synopsys

create ssl cert &lt;certFile> &lt;reqFile> &lt;certType> [-keyFile &lt;input_filename>] [-keyform ( DER | PEM )  {-PEMPassPhrase }] [-days &lt;positive_integer>] [-certForm ( DER | PEM )] [-CAcert &lt;input_filename>] [-CAcertForm ( DER | PEM )] [-CAkey &lt;input_filename>] [-CAkeyForm ( DER | PEM )] [-CAserial &lt;output_filename>]


##Arguments

<b>certFile</b>
Name for and, optionally, path to the generated certificate file. /nsconfig/ssl/ is the default path.
Maximum value: 63

<b>reqFile</b>
Name for and, optionally, path to the certificate-signing request (CSR). /nsconfig/ssl/ is the default path.
Maximum value: 63

<b>certType</b>
Type of certificate to generate. Specify one of the following:
* ROOT_CERT - Self-signed Root-CA certificate. You must specify the key file name. The generated Root-CA certificate can be used for signing end-user client or server certificates or to create Intermediate-CA certificates.
* INTM_CERT - Intermediate-CA certificate. 
* CLNT_CERT - End-user client certificate used for client authentication.
* SRVR_CERT - SSL server certificate used on SSL servers for end-to-end encryption.
Possible values: ROOT_CERT, INTM_CERT, CLNT_CERT, SRVR_CERT

<b>keyFile</b>
Name for and, optionally, path to the private key. You can either use an existing RSA or DSA key that you own or create a new private key on the NetScaler appliance. This file is required only when creating a self-signed Root-CA certificate. The key file is stored in the /nsconfig/ssl directory by default.                    
If the input key specified is an encrypted key, you are prompted to enter the PEM pass phrase that was used for encrypting the key.
Maximum value: 63

<b>keyform</b>
Format in which the key is stored on the appliance.
Possible values: DER, PEM
Default value: FORMAT_PEM

<b>PEMPassPhrase</b>

<b>days</b>
Number of days for which the certificate will be valid, beginning with the time and day (system time) of creation.
Default value: 365
Minimum value: 1
Maximum value: 3650

<b>certForm</b>
Format in which the certificate is stored on the appliance.
Possible values: DER, PEM
Default value: FORMAT_PEM

<b>CAcert</b>
Name of the CA certificate file that issues and signs the Intermediate-CA certificate or the end-user client and server certificates.
Maximum value: 63

<b>CAcertForm</b>
Format of the CA certificate.
Possible values: DER, PEM
Default value: FORMAT_PEM

<b>CAkey</b>
Private key, associated with the CA certificate that is used to sign the Intermediate-CA certificate or the end-user client and server certificate. If the CA key file is password protected, the user is prompted to enter the pass phrase that was used to encrypt the key.
Maximum value: 63

<b>CAkeyForm</b>
Format for the CA certificate.
Possible values: DER, PEM
Default value: FORMAT_PEM

<b>CAserial</b>
Serial number file maintained for the CA certificate. This file contains the serial number of the next certificate to be issued or signed by the CA. If the specified file does not exist, a new file is created, with /nsconfig/ssl/ as the default path. If you do not specify a proper path for the existing serial file, a new serial file is created. This might change the certificate serial numbers assigned by the CA certificate to each of the certificates it signs.
Maximum value: 63



##Example

1) create ssl cert /nsconfig/ssl/root_cert.pem /nsconfig/ssl/root_csr.pem ROOT_CERT -keyFile /nsconfig/ssl/root_key.pem -days 1000The above example creates a self signed Root-CA certificate.2) create ssl cert /nsconfig/ssl/server_cert.pem /nsconfig/ssl/server_csr.pem SRVR_CERT -CAcert /nsconfig/ssl/root_cert.pem -CAkey /nsconfig/ssl/root_key.pem -CAserial /nsconfig/ssl/root.srlThe above example creates a Server certificate which is signed by the Root-CA certificate: root_cert.pem

##Related Commands

<ul><li><a href="../../../ate-ssl-ce/ate-ssl-ce">create ssl certreq</a></li><li><a href="../../../te-ssl-r/te-ssl-r">create ssl rsakey</a></li><li><a href="../../../te-ssl-d/te-ssl-d">create ssl dsakey</a></li><li><a href="../../../-ssl-ce/-ssl-ce">add ssl certkey</a></li></ul>



