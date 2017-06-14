#filter action

The following operations can be performed on "filter action":


[add](#add-filter-action) | [rm](#rm-filter-action) | [set](#set-filter-action) | [unset](#unset-filter-action) | [show](#show-filter-action)

##add filter action

Creates a content filtering action. This action can be associated with a content filtering policy that is created with the add filter policy command. Note: The following content filtering actions are available by default:* RESET - Sends a TCP reset for the HTTP requests.* DROP - Drops the HTTP requests silently, without sending a TCP FIN for closing the connection.


##Synopsys

add filter action &lt;name> &lt;qual> [&lt;serviceName>] [&lt;value>] [&lt;respCode>] [&lt;page>]


##Arguments

<b>name</b>
Name for the filtering action. Must begin with a letter, number, or the underscore character (_). Other characters allowed, after the first character, are the hyphen (-), period (.) hash (#), space ( ), at sign (@), equals (=), and colon (:) characters. Choose a name that helps identify the type of action. The name of a filter action cannot be changed after it is created.
CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').

<b>qual</b>
Qualifier, which is the action to be performed. The qualifier cannot be changed after it is set. The available options function as follows:
ADD - Adds the specified HTTP header.
RESET - Terminates the connection, sending the appropriate termination notice to the user's browser.
FORWARD - Redirects the request to the designated service. You must specify either a service name or a page, but not both.
DROP - Silently deletes the request, without sending a response to the user's browser. 
CORRUPT - Modifies the designated HTTP header to prevent it from performing the function it was intended to perform, then sends the request/response to the server/browser.
ERRORCODE. Returns the designated HTTP error code to the user's browser (for example, 404, the standard HTTP code for a non-existent Web page).
Possible values: reset, add, corrupt, forward, errorcode, drop

<b>serviceName</b>
Service to which to forward HTTP requests. Required if the qualifier is FORWARD.

<b>value</b>
String containing the header_name and header_value. If the qualifier is ADD, specify &lt;header_name&gt;:&lt;header_value&gt;. If the qualifier is CORRUPT, specify only the header_name

<b>respCode</b>
Response code to be returned for HTTP requests (for use with the ERRORCODE qualifier).
Minimum value: 1

<b>page</b>
HTML page to return for HTTP requests (For use with the ERRORCODE qualifier).



##Example

add filter action bad_url_action errorcode 400 "&lt;HTML&gt;Bad URL.&lt;/HTML&gt;"add filter action forw_action FORWARD service1add filter action add_header_action add "HEADER:value"

##rm filter action

Removes a content filtering action. 


##Synopsys

rm filter action &lt;name>


##Arguments

<b>name</b>
Name of the content filter action to be removed.



##Example

rm filter action filter_action_name

##set filter action

Modifies an existing content filtering action.


##Synopsys

set filter action &lt;name> [-serviceName &lt;string>] [-value &lt;string>] [-respCode &lt;positive_integer>] [-page &lt;string>]


##Arguments

<b>name</b>
Name of the content filtering action to be modified.

<b>serviceName</b>
Service to which to forward HTTP requests. Required if the qualifier is FORWARD.

<b>value</b>
String containing the header_name and header_value. If the qualifier is ADD, specify &lt;header_name&gt;:&lt;header_value&gt;. If the qualifier is CORRUPT, specify only the header_name

<b>respCode</b>
Response code to be returned for HTTP requests (for use with the ERRORCODE qualifier).
Minimum value: 1

<b>page</b>
HTML page to return for HTTP requests (For use with the ERRORCODE qualifier).



##Example

set filter action bad_url_action -respcode 400 -page "&lt;HTML&gt;Bad URL.&lt;/HTML&gt;"set filter action forw_action -serviceName service1set filter action add_header_action -value "HEADER:value" 

##unset filter action

Use this command to remove filter action settings.Refer to the set filter action command for meanings of the arguments.


##Synopsys

unset filter action &lt;name> -page


##show filter action

Displays information about available filtering actions.


##Synopsys

show filter action [&lt;name>]


##Arguments

<b>name</b>
Name of the content filtering action to be displayed. If a name is not provided, information about all filter actions is shown.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>qual</b>
Qualifier, which is the action to be performed. The qualifier cannot be changed after it is set. The available options function as follows:
ADD - Adds the specified HTTP header.
RESET - Terminates the connection, sending the appropriate termination notice to the user's browser.
FORWARD - Redirects the request to the designated service. You must specify either a service name or a page, but not both.
DROP - Silently deletes the request, without sending a response to the user's browser. 
CORRUPT - Modifies the designated HTTP header to prevent it from performing the function it was intended to perform, then sends the request/response to the server/browser.
ERRORCODE. Returns the designated HTTP error code to the user's browser (for example, 404, the standard HTTP code for a non-existent Web page).

<b>serviceName</b>
The service to which HTTP requests are forwarded. This parameter will exist when the qualifier is FORWARD.

<b>value</b>
The string containing the header_name and header_value. When the qualifier is ADD it will have header_name:header_value. When the qualifier is Corrupt this will have header_name.

<b>respCode</b>
The response code to be returned for HTTP requests. This parameter will exist when the qualifier is ERRORCODE.

<b>page</b>
The HTML page that will be returned for the HTTP requests. This parameter will exist when the qualifier is ERRORCODE.

<b>stateflag</b>

<b>isDefault</b>
A value of true is returned if it is a default filteraction.

<b>flag</b>

<b>builtin</b>

<b>devno</b>

<b>count</b>



##Example

Example 1The following shows an example of the output of the show filter action command when no filter actions have been defined:1)      Name: RESET      Filter Type: reset2)      Name: DROP       Filter Type: drop DoneExample 2The following command creates a filter action:add filter action bad_url_action errorcode 400 "&lt;HTML&gt;Bad URL.&lt;/HTML&gt;"The following shows an example of the output of the show filter action command after the previous command has been issued:        Name: bad_url_action    Filter Type: errorcode        StatusCode: 400        Response Page: &lt;HTML&gt;Bad URL.&lt;/HTML&gt; Done

