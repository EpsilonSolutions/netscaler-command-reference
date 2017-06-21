#cmp action

The following operations can be performed on "cmp action":


[add](#add-cmp-action) | [rm](#rm-cmp-action) | [show](#show-cmp-action) | [set](#set-cmp-action) | [unset](#unset-cmp-action) | [rename](#rename-cmp-action)

##add cmp action

Creates a compression action. Note: User-defined compression actions supplement the built-in compression actions. The built-in compression actions, NOCOMPRESS, COMPRESS, GZIP, and DEFLATE, are always available.Available settings functions as follows:* NOCOMPRESS - Disables compression for data that matches the associated policy.* COMPRESS - Enable GZIP or DEFLATE compression, depending on which is supported by the browser.* GZIP - Enable GZIP compression. For browsers that do not support GZIP, compression is disabled.* DEFLATE - Enable DEFLATE compression for a specific policy. For browsers that do not support DEFLATE, compression is disabled.


##Synopsys

add cmp action &lt;name> &lt;cmpType> [-addVaryHeader &lt;addVaryHeader>  -varyHeaderValue &lt;string>]


##Arguments

<b>name</b>
Name of the compression action. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Can be changed after the action is added. 
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my cmp action" or 'my cmp action').

<b>cmpType</b>
Type of compression performed by this action. 
Available settings function as follows: 
* COMPRESS - Apply GZIP or DEFLATE compression to the response, depending on the request header. Prefer GZIP.
* GZIP - Apply GZIP compression.
* DEFLATE - Apply DEFLATE compression.
* NOCOMPRESS - Do not compress the response if the request matches a policy that uses this action.
Possible values: compress, gzip, deflate, nocompress

<b>addVaryHeader</b>
Control insertion of the Vary header in HTTP responses compressed by NetScaler. Intermediate caches store different versions of the response for different values of the headers present in the Vary response header.
Possible values: GLOBAL, DISABLED, ENABLED
Default value: GLOBAL

<b>varyHeaderValue</b>
The value of the HTTP Vary header for compressed responses.



##Example

add cmp action nocmp NOCOMPRESS

##rm cmp action

Removes the specified compression action.


##Synopsys

rm cmp action &lt;name>


##Arguments

<b>name</b>
Name of the action to be removed.



##Example

rm cmp action cmp_action_name

##show cmp action

Displays information about all the built-in and user-defined compression actions, or detailed information about the specified action.


##Synopsys

show cmp action [&lt;name>]


##Arguments

<b>name</b>
Name of the action for which to display detailed information.



##Outputs

<b>cmpType</b>
Type of compression performed by this action. 
Available settings function as follows: 
* COMPRESS - Apply GZIP or DEFLATE compression to the response, depending on the request header. Prefer GZIP.
* GZIP - Apply GZIP compression.
* DEFLATE - Apply DEFLATE compression.
* NOCOMPRESS - Do not compress the response if the request matches a policy that uses this action.

<b>deltaType</b>
The type of delta action if compression type is delta compression.

<b>addVaryHeader</b>
Control insertion of the Vary header in HTTP responses compressed by NetScaler. Intermediate caches store different versions of the response for different values of the headers present in the Vary response header.

<b>varyHeaderValue</b>
The value of the HTTP Vary header for compressed responses.

<b>stateflag</b>

<b>flags</b>

<b>builtin</b>
Flag to determine whether compression is default or not

<b>isDefault</b>
A value of true is returned if it is a default policy

<b>devno</b>

<b>count</b>



##Example

Example 1The following example shows output from the show cmp action command when no custom cmp actions have been defined:&gt; show cmp action        3 Compression actions:1)      Name: GZIP      Compression Type: gzip2)      Name: NOCOMPRESS        Compression Type: nocompress3)      Name: DEFLATE   Compression Type: deflate4)      Name: COMPRESS  Compression Type: compress Done DoneExample 2The following command creates a compression action:add cmp action nocmp NOCOMPRESSThe following example shows output from the show cmp action command after the previous command has been issued:&gt; show cmp action        3 Compression actions:1)      Name: GZIP      Compression Type: gzip2)      Name: NOCOMPRESS        Compression Type: nocompress3)      Name: DEFLATE   Compression Type: deflate4)      Name: COMPRESS  Compression Type: compress        1 Compression action:1)      Name: nocmp     Compression Type: nocompress Done

##set cmp action

Modifies the specified parameters of a compression action.


##Synopsys

set cmp action &lt;name> [-cmpType &lt;cmpType>] [-addVaryHeader &lt;addVaryHeader>  -varyHeaderValue &lt;string>]


##Arguments

<b>name</b>
Name of the compression action. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Can be changed after the action is added. 
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my cmp action" or 'my cmp action').

<b>cmpType</b>
Type of compression performed by this action. 
Available settings function as follows: 
* COMPRESS - Apply GZIP or DEFLATE compression to the response, depending on the request header. Prefer GZIP.
* GZIP - Apply GZIP compression.
* DEFLATE - Apply DEFLATE compression.
* NOCOMPRESS - Do not compress the response if the request matches a policy that uses this action.
Possible values: compress, gzip, deflate, nocompress

<b>addVaryHeader</b>
Control insertion of the Vary header in HTTP responses compressed by NetScaler. Intermediate caches store different versions of the response for different values of the headers present in the Vary response header.
Possible values: GLOBAL, DISABLED, ENABLED
Default value: GLOBAL

<b>varyHeaderValue</b>
The value of the HTTP Vary header for compressed responses.



##Example

set cmp action cmpact1 -addVaryHeader ENABLED -varyHeaderValue User-Agent

##unset cmp action

Use this command to remove cmp action settings.Refer to the set cmp action command for meanings of the arguments.


##Synopsys

unset cmp action &lt;name> -addVaryHeader


##rename cmp action

Renames a compression action.


##Synopsys

rename cmp action &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the action.

<b>newName</b>
New name for the compression action. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at
(@), equals (=), and hyphen (-) characters. 
Choose a name that can be correlated with the function that the action performs. 
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my cmp action" or 'my cmp action').



##Example

rename cmp policy oldname newname

