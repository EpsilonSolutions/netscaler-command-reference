#ca action

The following operations can be performed on "ca action":


[add](#add-ca-action) | [show](#show-ca-action) | [set](#set-ca-action) | [unset](#unset-ca-action) | [rm](#rm-ca-action) | [rename](#rename-ca-action)

##add ca action

Creates a content adapation action. This action must later be invoked in the 'add ca policy' command.


##Synopsys

add ca action &lt;name> [-accumResSize &lt;KBytes>] [-lbvserver &lt;string>] [-comment &lt;string>] -type &lt;type>


##Arguments

<b>name</b>
Name of the content accelerator action. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.

<b>accumResSize</b>
Size of the data, in KB, that the server must respond with. The NetScaler uses this data to compute a hash which is then used to lookup within the T2100 appliance.

<b>lbvserver</b>
Name of the load balancing virtual server that has the T2100 appliances as services.

<b>comment</b>
Information about the content accelerator action.

<b>type</b>
Specifies whether the NetScaler must lookup for the response on the T2100 appliance or serve the response directly from the server.
Possible values: nolookup, lookup, noop



##show ca action

Displays information about a content accelerator action. If no name is specified, this command displays information of all available content accelerator actions.


##Synopsys

show ca action [&lt;name>]


##Arguments

<b>name</b>
Name of the content accelerator action.



##Outputs

<b>type</b>
Type of content accelerator action.

<b>stateflag</b>

<b>accumResSize</b>
Size of the data, in KB, that the server must respond with. The NetScaler uses this data to compute a hash which is then used to lookup within the T2100 appliance.

<b>lbvserver</b>
Name of the load balancing virtual server that has the T2100 appliances as services.

<b>isDefault</b>
A value of true is returned if it is a default content accelerator action.

<b>hits</b>
The number of times the action has been taken.

<b>builtin</b>
Flag to determine whether content accelerator action is built-in or not

<b>flags</b>

<b>comment</b>
Information about the content accelerator action.

<b>devno</b>

<b>count</b>



##Example

1. show ca action	2. show ca action act_insert

##set ca action

Modifies the specified parameters of a Content Accelerator action.


##Synopsys

set ca action &lt;name> [-accumResSize &lt;KBytes>] [-type &lt;type>] [-lbvserver &lt;string>] [-comment &lt;string>]


##Arguments

<b>name</b>
Name of the Content Accelerator policy to modify.

<b>accumResSize</b>
Size of the data, in KB, that the server must respond with. The NetScaler uses this data to compute a hash which is then used to lookup within the T2100 appliance.

<b>type</b>
Specifies whether the NetScaler must lookup for the response on the T2100 appliance or serve the response directly from the server.
Possible values: nolookup, lookup, noop

<b>lbvserver</b>
Name of the load balancing virtual server that has the T2100 appliances as services.

<b>comment</b>
Information about the content accelerator action.



##Example

set ca action caact1 -accumresize 43"

##unset ca action

Use this command to remove ca action settings.Refer to the set ca action command for meanings of the arguments.


##Synopsys

unset ca action &lt;name> [-accumResSize] [-type] [-lbvserver] [-comment]


##rm ca action

Removes a ca action.


##Synopsys

rm ca action &lt;name>


##Arguments

<b>name</b>
Name of the Content Accelerator action to remove.



##Example

rm ca action act_before

##rename ca action

Renames a Content Accelerator action.


##Synopsys

rename ca action &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the Content Accelerator action.

<b>newName</b>
New name for the content accelerator action. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Can be changed after the content accelerator policy is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my content accelerator action" or 'my content accelerator action').



##Example

rename ca action oldname newname

