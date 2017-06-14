#ssl keyFile

The following operations can be performed on "ssl keyFile":


[import](#import-ssl-keyfile) | [rm](#rm-ssl-keyfile) | [show](#show-ssl-keyfile)

##import ssl keyFile

Imports a key file to the NetScaler appliance, assigns it a name, and stores it in the /nsconfig/ssl/keyfilefolder. The folder is created if it does not exist.


##Synopsys

import ssl keyFile &lt;name> &lt;src>


##Arguments

<b>name</b>
Name to assign to the imported key file. Must begin with an ASCII alphanumeric or underscore(_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@),equals (=), and hyphen (-) characters. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my file" or 'my file').

<b>src</b>
URL specifying the protocol, host, and path, including file name, to the key file to be imported. For example, http://www.example.com/key_file.
NOTE: The import fails if the object to be imported is on an HTTPS server that requires client certificate authentication for access.



##Example

import ssl keyfile my-keyfile http://www.example.com/key_file

##rm ssl keyFile

Deletes the specified key file.


##Synopsys

rm ssl keyFile &lt;name>


##Arguments

<b>name</b>
Name of the key file to be delete.



##Example

rm ssl keyfile &lt;name&gt;

##show ssl keyFile

Displays lists of all the imported key file objects on the NetScaler ADC.


##Synopsys

show ssl keyFile


##Arguments

<b>summary</b>

<b>fullValues</b>



##Outputs

<b>name</b>
Name to assign to the imported key file. Must begin with an ASCII alphanumeric or underscore(_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@),equals (=), and hyphen (-) characters. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my file" or 'my file').

<b>src</b>
URL specifying the protocol, host, and path, including file name, to the key file to be imported. For example, http://www.example.com/key_file.
NOTE: The import fails if the object to be imported is on an HTTPS server that requires client certificate authentication for access.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show ssl keyfile

