#ssl pkcs8

The following operations can be performed on "ssl pkcs8":


##convert ssl pkcs8

Convert a PEM or DER format key file to PKCS#8 format before importing it into the FIPS appliance.


##Synopsys

convert ssl pkcs8 &lt;pkcs8File> &lt;keyFile> [-keyform ( DER | PEM )] {-password }


##Arguments

<b>pkcs8File</b>
Name for and, optionally, path to, the output file where the PKCS#8 format key file is stored. /nsconfig/ssl/ is the default path.
Maximum value: 63

<b>keyFile</b>
Name of and, optionally, path to the input key file to be converted from PEM or DER format to PKCS#8 format. /nsconfig/ssl/ is the default path.
Maximum value: 63

<b>keyform</b>
Format in which the key file is stored on the appliance.
Possible values: DER, PEM
Default value: PEM

<b>password</b>
Password to assign to the file if the key is encrypted. Applies only for PEM format files.
Maximum value: 31



##Example

convert ssl pkcs8 /nsconfig/ssl/key.pk8 /nsconfig/ssl/key.pem

