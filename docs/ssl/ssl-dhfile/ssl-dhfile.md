#ssl dhFile

The following operations can be performed on "ssl dhFile":


[import](#import-ssl-dhfile) | [rm](#rm-ssl-dhfile) | [show](#show-ssl-dhfile)

##import ssl dhFile

Imports a DH file to the NetScaler appliance, assigns it a name, and stores it in the /nsconfig/ssl/dhfile folder. The folder is created if it does not exist.


##Synopsys

import ssl dhFile &lt;name> &lt;src>


##Arguments

<b>name</b>
Name to assign to the imported DH file.  Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my file" or 'my file').

<b>src</b>
URL specifying the protocol, host, and path, including file name, to the DH file to be imported. For example, http://www.example.com/dh_file.  
NOTE: The import fails if the file is on an HTTPS server that requires client certificate authentication for access.



##Example

import ssl dhfile my-dhfile http://www.example.com/dh_file

##rm ssl dhFile

Deletes the specified DH file.


##Synopsys

rm ssl dhFile &lt;name>


##Arguments

<b>name</b>
Name of the DH file to delete.



##Example

rm ssl dhfile my-dhfile

##show ssl dhFile

Displays a list of all the imported DH file objects on the NetScaler ADC.


##Synopsys

show ssl dhFile


##Outputs

<b>name</b>
Name to assign to the imported DH file.  Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my file" or 'my file').

<b>src</b>
URL specifying the protocol, host, and path, including file name, to the DH file to be imported. For example, http://www.example.com/dh_file.  
NOTE: The import fails if the file is on an HTTPS server that requires client certificate authentication for access.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show ssl dhfile

