#ssl crlFile

The following operations can be performed on "ssl crlFile":


[import](#import-ssl-crlfile) | [rm](#rm-ssl-crlfile) | [show](#show-ssl-crlfile)

##import ssl crlFile

Imports a CRL file to the NetScaler appliance, assigns it a name, and stores it in the /var/netscaler/ssl/crlfile folder. The folder is created if it does not exist.


##Synopsys

import ssl crlFile &lt;name> &lt;src>


##Arguments

<b>name</b>
Name to assign to the imported CRL file. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my file" or 'my file').

<b>src</b>
URL specifying the protocol, host, and path, including file name to the CRL file to be imported. For example, http://www.example.com/crl_file.
NOTE: The import fails if the object to be imported is on an HTTPS server that requires client certificate authentication for access.



##Example

import ssl crlfile my-crlfile http://www.example.com/crl_file

##rm ssl crlFile

Deletes the specified CRL file.


##Synopsys

rm ssl crlFile &lt;name>


##Arguments

<b>name</b>
Name of the CRL file to delete.



##Example

rm ssl crlfile my-crlfile

##show ssl crlFile

Displays lists of all the imported CRL file objects on the NetScaler ADC.


##Synopsys

show ssl crlFile


##Arguments

<b>summary</b>

<b>fullValues</b>



##Outputs

<b>name</b>
Name to assign to the imported CRL file. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my file" or 'my file').

<b>src</b>
URL specifying the protocol, host, and path, including file name to the CRL file to be imported. For example, http://www.example.com/crl_file.
NOTE: The import fails if the object to be imported is on an HTTPS server that requires client certificate authentication for access.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show ssl crlfile

