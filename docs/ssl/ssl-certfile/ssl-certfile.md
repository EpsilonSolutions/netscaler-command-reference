#ssl certFile

The following operations can be performed on "ssl certFile":


[import](#import-ssl-certfile) | [rm](#rm-ssl-certfile) | [show](#show-ssl-certfile)

##import ssl certFile

Imports a certificate file to the NetScaler appliance, assigns it a name, and stores it in the /nsconfig/ssl/certfile folder. The folder is created if it does not exist.


##Synopsys

import ssl certFile &lt;name> &lt;src>


##Arguments

<b>name</b>
Name to assign to the imported certificate file. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my file" or 'my file').

<b>src</b>
URL specifying the protocol, host, and path, including file name, to the certificate file to be imported. For example, http://www.example.com/cert_file.
NOTE: The import fails if the object to be imported is on an HTTPS server that requires client certificate authentication for access.



##Example

import ssl certfile my-certfile http://www.example.com/cert_file

##rm ssl certFile

Deletes the specified certificate file.


##Synopsys

rm ssl certFile &lt;name>


##Arguments

<b>name</b>
Name of the certificate file to delete.



##Example

rm ssl certfile my-certfile

##show ssl certFile

Displays a list of all the imported certificate file objects on the NetScaler ADC.


##Synopsys

show ssl certFile


##Outputs

<b>name</b>
Name to assign to the imported certificate file. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my file" or 'my file').

<b>src</b>
URL specifying the protocol, host, and path, including file name, to the certificate file to be imported. For example, http://www.example.com/cert_file.
NOTE: The import fails if the object to be imported is on an HTTPS server that requires client certificate authentication for access.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show ssl certfile

