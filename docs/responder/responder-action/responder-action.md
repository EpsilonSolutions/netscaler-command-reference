#responder action

The following operations can be performed on "responder action":


[add](#add-responder-action) | [rm](#rm-responder-action) | [set](#set-responder-action) | [unset](#unset-responder-action) | [show](#show-responder-action) | [rename](#rename-responder-action)

##add responder action

Creates a responder action, which specifies how to respond to a request.


##Synopsys

add responder action &lt;name> &lt;type> (&lt;target> | &lt;htmlpage>) [-comment &lt;string>] [-responseStatusCode &lt;positive_integer>] [-reasonPhrase &lt;string>]


##Arguments

<b>name</b>
Name for the responder action. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Can be changed after the responder policy is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my responder action" or 'my responder action').

<b>type</b>
Type of responder action. Available settings function as follows:
* respondwith &lt;target&gt; - Respond to the request with the expression specified as the target.
* respondwithhtmlpage - Respond to the request with the uploaded HTML page object specified as the target.
* redirect - Redirect the request to the URL specified as the target.
* sqlresponse_ok - Send an SQL OK response.
* sqlresponse_error - Send an SQL ERROR response.
Possible values: noop, respondwith, redirect, respondwithhtmlpage, sqlresponse_ok, sqlresponse_error

<b>target</b>
Expression specifying what to respond with. Typically a URL for redirect policies or a default-syntax expression.  In addition to NetScaler default-syntax expressions that refer to information in the request, a stringbuilder expression can contain text and HTML, and simple escape codes that define new lines and paragraphs. Enclose each stringbuilder expression element (either a NetScaler default-syntax expression or a string) in double quotation marks. Use the plus (+) character to join the elements. 
Examples:
1) Respondwith expression that sends an HTTP 1.1 200 OK response:
"HTTP/1.1 200 OK\\r\\n\\r\\n"
2) Redirect expression that redirects user to the specified web host and appends the request URL to the redirect.
"http://backupsite2.com" + HTTP.REQ.URL
3) Respondwith expression that sends an HTTP 1.1 404 Not Found response with the request URL included in the response:
"HTTP/1.1 404 Not Found\\r\\n\\r\\n"+ "HTTP.REQ.URL.HTTP_URL_SAFE" + "does not exist on the web server."
The following requirement applies only to the NetScaler CLI:
Enclose the entire expression in single quotation marks. (NetScaler default expression elements should be included inside the single quotation marks for the entire expression, but do not need to be enclosed in double quotation marks.)

<b>htmlpage</b>
For respondwithhtmlpage policies, name of the HTML page object to use as the response. You must first import the page object.

<b>comment</b>
Comment. Any type of information about this responder action.

<b>responseStatusCode</b>
HTTP response status code, for example 200, 302, 404, etc. The default value for the redirect action type is 302 and for respondwithhtmlpage is 200
Minimum value: 100
Maximum value: 599

<b>reasonPhrase</b>
Expression specifying the reason phrase of the HTTP response. The reason phrase may be a string literal with quotes or a PI expression. For example: "Invalid URL: " + HTTP.REQ.URL



##Example

1) add responder action act1 respondwith "\\\\"HTTP/1.1 200 OK\\\\r\\\\n\\\\r\\\\n\\\\""2) add responder action resp respondwithhtmlpage my-responder-page,3) add responder action redir_action redirect '"http://backupsite2.com" + HTTP.REQ.URL'

##rm responder action

Removes the specified responder action.


##Synopsys

rm responder action &lt;name>


##Arguments

<b>name</b>
Name of the responder action to remove.



##Example

rm responder action act_before

##set responder action

Modifies the specified parameters of a responder action.


##Synopsys

set responder action &lt;name> [-target &lt;string>] [-htmlpage &lt;string>] [-responseStatusCode &lt;positive_integer>] [-reasonPhrase &lt;string>] [-comment &lt;string>]


##Arguments

<b>name</b>
Name of the responder action to be modified.

<b>target</b>
Expression specifying what to respond with. Typically a URL for redirect policies or a default-syntax expression.  In addition to NetScaler default-syntax expressions that refer to information in the request, a stringbuilder expression can contain text and HTML, and simple escape codes that define new lines and paragraphs. Enclose each stringbuilder expression element (either a NetScaler default-syntax expression or a string) in double quotation marks. Use the plus (+) character to join the elements. 
Examples:
1) Respondwith expression that sends an HTTP 1.1 200 OK response:
"HTTP/1.1 200 OK\\r\\n\\r\\n"
2) Redirect expression that redirects user to the specified web host and appends the request URL to the redirect.
"http://backupsite2.com" + HTTP.REQ.URL
3) Respondwith expression that sends an HTTP 1.1 404 Not Found response with the request URL included in the response:
"HTTP/1.1 404 Not Found\\r\\n\\r\\n"+ "HTTP.REQ.URL.HTTP_URL_SAFE" + "does not exist on the web server."
The following requirement applies only to the NetScaler CLI:
Enclose the entire expression in single quotation marks. (NetScaler default expression elements should be included inside the single quotation marks for the entire expression, but do not need to be enclosed in double quotation marks.)

<b>htmlpage</b>
For respondwithhtmlpage policies, name of the HTML page object to use as the response. You must first import the page object.

<b>responseStatusCode</b>
HTTP response status code, for example 200, 302, 404, etc. The default value for the redirect action type is 302 and for respondwithhtmlpage is 200
Minimum value: 100
Maximum value: 599

<b>reasonPhrase</b>
Expression specifying the reason phrase of the HTTP response. The reason phrase may be a string literal with quotes or a PI expression. For example: "Invalid URL: " + HTTP.REQ.URL

<b>comment</b>
Comment. Any type of information about this responder action.



##Example

1. set responder action act_responder -target 'HTTP.REQ.HEADER(MYURL) -redirectresponsecode &lt;respcode&gt;'/,2. set responder action act_responder -htmlpage my-local-file 

##unset responder action

Use this command to remove responder action settings.Refer to the set responder action command for meanings of the arguments.


##Synopsys

unset responder action &lt;name> [-responseStatusCode] [-reasonPhrase] [-comment]


##show responder action

Displays the current settings for the specified responder action.If no action name is provided, displays a list of all responder actions currently configured on the NetScaler appliance, with abbreviated settings.


##Synopsys

show responder action [&lt;name>]


##Arguments

<b>name</b>
Name of the responder action.



##Outputs

<b>stateflag</b>

<b>type</b>
Type of responder action. It can be: (respondwith).

<b>target</b>
Expression specifying what to to respond with

<b>htmlpage</b>
Option specifying to respondwith htmlpage

<b>bypassSafetyCheck</b>
The safety check to allow unsafe expressions.

<b>hits</b>
The number of times the action has been taken.

<b>referenceCount</b>
The number of references to the action.

<b>undefHits</b>
The number of times the action resulted in UNDEF.

<b>comment</b>
Comment. Any type of information about this responder action.

<b>builtin</b>
Flag to determine whether responder action is built-in or not

<b>responseStatusCode</b>
HTTP response status code, for example 200, 302, 404, etc. The default value for the redirect action type is 302 and for respondwithhtmlpage is 200

<b>reasonPhrase</b>
Expression specifying the reason phrase of the HTTP response. The reason phrase may be a string literal with quotes or a PI expression. For example: "Invalid URL: " + HTTP.REQ.URL

<b>devno</b>

<b>count</b>



##Example

1. show responder action	2. show responder action act_insert

##rename responder action

Renames a responder action.


##Synopsys

rename responder action &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the responder action.

<b>newName</b>
New name for the responder action.
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my responder action" or my responder action').



##Example

rename responder action oldname newname

