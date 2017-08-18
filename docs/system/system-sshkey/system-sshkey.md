#system sshkey

The following operations can be performed on "system sshkey":


[rm](#rm-system-sshkey) | [import](#import-system-sshkey) | [show](#show-system-sshkey)

##rm system sshkey

Remove the public or private key


##Synopsys

rm system sshkey &lt;name> -sshkeytype ( PRIVATE | PUBLIC )


##Arguments

<b>name</b>
URL \\(protocol, host, path, and file name\\) from where the location file will be imported.
            NOTE: The import fails if the object to be imported is on an HTTPS server that requires client certificate authentication for access.

<b>sshkeytype</b>
The type of the ssh key whether public or private key
Possible values: PRIVATE, PUBLIC



##import system sshkey

Import the ssh key.


##Synopsys

import system sshkey &lt;name> -src &lt;URL> -sshkeytype ( PRIVATE | PUBLIC )


##Arguments

<b>name</b>
URL \\(protocol, host, path, and file name\\) from where the location file will be imported.
            NOTE: The import fails if the object to be imported is on an HTTPS server that requires client certificate authentication for access.

<b>src</b>
URL \\(protocol, host, path, and file name\\) from where the location file will be imported.
            NOTE: The import fails if the object to be imported is on an HTTPS server that requires client certificate authentication for access.

<b>sshkeytype</b>
The type of the ssh key whether public or private key
Possible values: PRIVATE, PUBLIC



##show system sshkey

Show the private key


##Synopsys

show system sshkey [-sshkeytype ( PRIVATE | PUBLIC )]


##Arguments

<b>sshkeytype</b>
The type of the ssh key whether public or private key
Possible values: PRIVATE, PUBLIC



##Outputs

<b>name</b>
URL \\(protocol, host, path, and file name\\) from where the location file will be imported.
            NOTE: The import fails if the object to be imported is on an HTTPS server that requires client certificate authentication for access.



