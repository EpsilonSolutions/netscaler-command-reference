#ns centralmanagementserver

The following operations can be performed on "ns centralmanagementserver":


[add](#add-ns-centralmanagementserver) | [rm](#rm-ns-centralmanagementserver) | [show](#show-ns-centralmanagementserver)

##add ns centralmanagementserver

Adds a centralmgmtserver server profile and verifies the configuration to ensure that it is correct. Also registers the device on the central management server.


##Synopsys

add ns centralmanagementserver &lt;type> &lt;userName> [-IPAddress &lt;ip_addr|ipv6_addr|*> | -serverName &lt;string>]


##Arguments

<b>type</b>
Type of the central management server. Must be either CLOUD or ONPREM depending on whether the server is on the cloud or on premise.
Possible values: CLOUD, ONPREM

<b>userName</b>
Username for access to central management server. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or
single quotation marks (for example, "my ns centralmgmtserver" or "my ns centralmgmtserver").

<b>password</b>
Password for access to central management server. Required for any user account.

<b>IPAddress</b>
Ip Address of central management server.

<b>serverName</b>
Fully qualified domain name of the central management server.



##Example

add ns centralmgmtserver cloud johndoe abcdThe above example adds user johndoe with password abcd

##rm ns centralmanagementserver

Removes a central management server profile and the associated configuration.


##Synopsys

rm ns centralmanagementserver &lt;type>


##Arguments

<b>type</b>
Type of the centralmgmtserver user to remove.
Possible values: CLOUD, ONPREM



##show ns centralmanagementserver

Displays the current configuration of a central management server profile.


##Synopsys

show ns centralmanagementserver [&lt;type>]


##Arguments

<b>type</b>
Type of the central management server profile.
Possible values: CLOUD, ONPREM



##Outputs

<b>userName</b>
Username for access to the central management server.

<b>IPAddress</b>
Ip Address of central management server.

<b>serverName</b>
Fully qualified domain name of the central management server.

<b>password</b>
Password for access to the central management server.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

Example&gt; show ns centralmgmtserver ONPREM        Type: ONPREM            UserName: joe        IPAddress: 10.102.1.123        Password: b04b0ac4e363c4b05d9a3e84cfbfd75763d11c5546ca7d4abb133a249ea8440e Done&gt;

