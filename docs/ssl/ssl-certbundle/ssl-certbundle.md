#ssl certBundle

The following operations can be performed on "ssl certBundle":


[import](#import-ssl-certbundle) | [rm](#rm-ssl-certbundle) | [show](#show-ssl-certbundle) | [apply](#apply-ssl-certbundle) | [export](#export-ssl-certbundle)

##import ssl certBundle

Imports a certificate bundle to the NetScaler appliance, assigns it a name, and stores it.


##Synopsys

import ssl certBundle &lt;name> &lt;src>


##Arguments

<b>name</b>
Name to assign to the imported certificate bundle. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my file" or 'my file').

<b>src</b>
URL specifying the protocol, host, and path, including file name, to the certificate bundle to be imported or exported. For example, http://www.example.com/cert_bundle_file.
NOTE: The import fails if the object to be imported is on an HTTPS server that requires client certificate authentication for access.



##Example

import ssl certbundle my-certbundle http://www.example.com/cert_bundle

##rm ssl certBundle

Deletes the specified certificate bundle.


##Synopsys

rm ssl certBundle &lt;name>


##Arguments

<b>name</b>
Name to assign to the imported certificate bundle. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my file" or 'my file').



##Example

rm ssl certbundle my-certbundle

##show ssl certBundle

Displays a list of all the imported certificate bundle objects on the NetScaler ADC.


##Synopsys

show ssl certBundle


##Outputs

<b>name</b>
Name to assign to the imported certificate bundle. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my file" or 'my file').

<b>inUse</b>

<b>src</b>
URL specifying the protocol, host, and path, including file name, to the certificate bundle to be imported or exported. For example, http://www.example.com/cert_bundle_file.
NOTE: The import fails if the object to be imported is on an HTTPS server that requires client certificate authentication for access.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show ssl certbundle

##apply ssl certBundle

Applies the specified CA certificate bundle and the device starts using the applied CA bundle to validate the server certificate. Use 'apply ssl certBundle DEFAULT' to restore the default CA certificate bundle.


##Synopsys

apply ssl certBundle &lt;name>


##Arguments

<b>name</b>
Name to assign to the imported certificate bundle. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my file" or 'my file').



##Example

apply ssl certbundle my-certbundle

##export ssl certBundle

Exports a certificate bundle from one appliance to another for backup or editing purpose. 


##Synopsys

export ssl certBundle &lt;name> &lt;src>


##Arguments

<b>name</b>
Name to assign to the imported certificate bundle. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my file" or 'my file').

<b>src</b>
URL specifying the protocol, host, and path, including file name, to the certificate bundle to be imported or exported. For example, http://www.example.com/cert_bundle_file.
NOTE: The import fails if the object to be imported is on an HTTPS server that requires client certificate authentication for access.



##Example

export ssl certbundle my-certbundle

