#authentication webAuthAction

The following operations can be performed on "authentication webAuthAction":


[add](#add-authentication-webauthaction) | [rm](#rm-authentication-webauthaction) | [set](#set-authentication-webauthaction) | [unset](#unset-authentication-webauthaction) | [show](#show-authentication-webauthaction)

##add authentication webAuthAction

Adds an action to be used for web authentication.* Specify the entire HTTP request in a single expression.


##Synopsys

add authentication webAuthAction &lt;name> -serverIP &lt;ip_addr|ipv6_addr|*> -serverPort &lt;port|*> [-fullReqExpr &lt;string>] -scheme ( http | https ) -successRule &lt;expression> [-defaultAuthenticationGroup &lt;string>] [-Attribute1 &lt;string>] [-Attribute2 &lt;string>] [-Attribute3 &lt;string>] [-Attribute4 &lt;string>] [-Attribute5 &lt;string>] [-Attribute6 &lt;string>] [-Attribute7 &lt;string>] [-Attribute8 &lt;string>] [-Attribute9 &lt;string>] [-Attribute10 &lt;string>] [-Attribute11 &lt;string>] [-Attribute12 &lt;string>] [-Attribute13 &lt;string>] [-Attribute14 &lt;string>] [-Attribute15 &lt;string>] [-Attribute16 &lt;string>]


##Arguments

<b>name</b>
Name for the Web Authentication action. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the profile is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my authentication action? or ?my authentication action?).

<b>serverIP</b>
IP address of the web server to be used for authentication.

<b>serverPort</b>
Port on which the web server accepts connections.
Minimum value: 1

<b>fullReqExpr</b>
Exact HTTP request, in the form of a default syntax expression, which the NetScaler appliance sends to the authentication server.
The NetScaler appliance does not check the validity of this request. One must manually validate the request.

<b>scheme</b>
Type of scheme for the web server.
Possible values: http, https

<b>successRule</b>
Expression, that checks to see if authentication is successful.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.
Maximum value: 64

<b>Attribute1</b>
Expression that would be evaluated to extract attribute1 from the webauth response
Maximum value: 64

<b>Attribute2</b>
Expression that would be evaluated to extract attribute2 from the webauth response
Maximum value: 64

<b>Attribute3</b>
Expression that would be evaluated to extract attribute3 from the webauth response
Maximum value: 64

<b>Attribute4</b>
Expression that would be evaluated to extract attribute4 from the webauth response
Maximum value: 64

<b>Attribute5</b>
Expression that would be evaluated to extract attribute5 from the webauth response
Maximum value: 64

<b>Attribute6</b>
Expression that would be evaluated to extract attribute6 from the webauth response
Maximum value: 64

<b>Attribute7</b>
Expression that would be evaluated to extract attribute7 from the webauth response
Maximum value: 64

<b>Attribute8</b>
Expression that would be evaluated to extract attribute8 from the webauth response
Maximum value: 64

<b>Attribute9</b>
Expression that would be evaluated to extract attribute9 from the webauth response
Maximum value: 64

<b>Attribute10</b>
Expression that would be evaluated to extract attribute10 from the webauth response
Maximum value: 64

<b>Attribute11</b>
Expression that would be evaluated to extract attribute11 from the webauth response
Maximum value: 64

<b>Attribute12</b>
Expression that would be evaluated to extract attribute12 from the webauth response
Maximum value: 64

<b>Attribute13</b>
Expression that would be evaluated to extract attribute13 from the webauth response
Maximum value: 64

<b>Attribute14</b>
Expression that would be evaluated to extract attribute14 from the webauth response
Maximum value: 64

<b>Attribute15</b>
Expression that would be evaluated to extract attribute15 from the webauth response
Maximum value: 64

<b>Attribute16</b>
Expression that would be evaluated to extract attribute16 from the webauth response
Maximum value: 64



##Example

add authentication webAuthAction a1 -ServerIP 1.1.1.1 -ServerPort 80 -scheme HTTP -successRule true -fullReqExpr &lt;http request string&gt;

##rm authentication webAuthAction

Removes a web authentication action. You cannot remove an action that is used in any part of a policy.


##Synopsys

rm authentication webAuthAction &lt;name>


##Arguments

<b>name</b>
Name of the web authentication action to remove.



##Example

rm authentication webAuthAction a1

##set authentication webAuthAction

Modifies the attributes of an existing web authentication action.


##Synopsys

set authentication webAuthAction &lt;name> [-serverIP &lt;ip_addr|ipv6_addr|*>] [-serverPort &lt;port|*>] [-fullReqExpr &lt;string>] [-scheme ( http | https )] [-successRule &lt;expression>] [-defaultAuthenticationGroup &lt;string>] [-Attribute1 &lt;string>] [-Attribute2 &lt;string>] [-Attribute3 &lt;string>] [-Attribute4 &lt;string>] [-Attribute5 &lt;string>] [-Attribute6 &lt;string>] [-Attribute7 &lt;string>] [-Attribute8 &lt;string>] [-Attribute9 &lt;string>] [-Attribute10 &lt;string>] [-Attribute11 &lt;string>] [-Attribute12 &lt;string>] [-Attribute13 &lt;string>] [-Attribute14 &lt;string>] [-Attribute15 &lt;string>] [-Attribute16 &lt;string>]


##Arguments

<b>name</b>
Name of the action to configure.

<b>serverIP</b>
IP address of the web server to be used for authentication.

<b>serverPort</b>
Port on which the web server accepts connections.
Minimum value: 1

<b>fullReqExpr</b>
Exact HTTP request, in the form of a default syntax expression, which the NetScaler appliance sends to the authentication server.
The NetScaler appliance does not check the validity of this request. One must manually validate the request.

<b>scheme</b>
Type of scheme for the web server.
Possible values: http, https

<b>successRule</b>
Expression, that checks to see if authentication is successful.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.
Maximum value: 64

<b>Attribute1</b>
Expression that would be evaluated to extract attribute1 from the webauth response
Maximum value: 64

<b>Attribute2</b>
Expression that would be evaluated to extract attribute2 from the webauth response
Maximum value: 64

<b>Attribute3</b>
Expression that would be evaluated to extract attribute3 from the webauth response
Maximum value: 64

<b>Attribute4</b>
Expression that would be evaluated to extract attribute4 from the webauth response
Maximum value: 64

<b>Attribute5</b>
Expression that would be evaluated to extract attribute5 from the webauth response
Maximum value: 64

<b>Attribute6</b>
Expression that would be evaluated to extract attribute6 from the webauth response
Maximum value: 64

<b>Attribute7</b>
Expression that would be evaluated to extract attribute7 from the webauth response
Maximum value: 64

<b>Attribute8</b>
Expression that would be evaluated to extract attribute8 from the webauth response
Maximum value: 64

<b>Attribute9</b>
Expression that would be evaluated to extract attribute9 from the webauth response
Maximum value: 64

<b>Attribute10</b>
Expression that would be evaluated to extract attribute10 from the webauth response
Maximum value: 64

<b>Attribute11</b>
Expression that would be evaluated to extract attribute11 from the webauth response
Maximum value: 64

<b>Attribute12</b>
Expression that would be evaluated to extract attribute12 from the webauth response
Maximum value: 64

<b>Attribute13</b>
Expression that would be evaluated to extract attribute13 from the webauth response
Maximum value: 64

<b>Attribute14</b>
Expression that would be evaluated to extract attribute14 from the webauth response
Maximum value: 64

<b>Attribute15</b>
Expression that would be evaluated to extract attribute15 from the webauth response
Maximum value: 64

<b>Attribute16</b>
Expression that would be evaluated to extract attribute16 from the webauth response
Maximum value: 64



##Example

set authentication webAuthAction a1 -ServerIP 1.1.1.1 -ServerPort 80

##unset authentication webAuthAction

Use this command to remove authentication webAuthAction settings.Refer to the set authentication webAuthAction command for meanings of the arguments.


##Synopsys

unset authentication webAuthAction &lt;name> [-serverIP] [-serverPort] [-fullReqExpr] [-defaultAuthenticationGroup] [-Attribute1] [-Attribute2] [-Attribute3] [-Attribute4] [-Attribute5] [-Attribute6] [-Attribute7] [-Attribute8] [-Attribute9] [-Attribute10] [-Attribute11] [-Attribute12] [-Attribute13] [-Attribute14] [-Attribute15] [-Attribute16]


##show authentication webAuthAction

Displays information about the configured web authentication action.


##Synopsys

show authentication webAuthAction [&lt;name>]


##Arguments

<b>name</b>
Name of the web authentication action to display. If a name is not provided, information about all actions is shown.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>serverIP</b>
IP address of the web server to be used for authentication.

<b>serverPort</b>
Port on which the web server accepts connections.

<b>fullReqExpr</b>
Exact HTTP request, in the form of a default syntax expression, which the NetScaler appliance sends to the authentication server.
The NetScaler appliance does not check the validity of this request. One must manually validate the request.

<b>scheme</b>
Type of scheme for the web server.

<b>successRule</b>
Expression, that checks to see if authentication is successful.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.

<b>Attribute1</b>
Expression that would be evaluated to extract attribute1 from the webauth response

<b>Attribute2</b>
Expression that would be evaluated to extract attribute2 from the webauth response

<b>Attribute3</b>
Expression that would be evaluated to extract attribute3 from the webauth response

<b>Attribute4</b>
Expression that would be evaluated to extract attribute4 from the webauth response

<b>Attribute5</b>
Expression that would be evaluated to extract attribute5 from the webauth response

<b>Attribute6</b>
Expression that would be evaluated to extract attribute6 from the webauth response

<b>Attribute7</b>
Expression that would be evaluated to extract attribute7 from the webauth response

<b>Attribute8</b>
Expression that would be evaluated to extract attribute8 from the webauth response

<b>Attribute9</b>
Expression that would be evaluated to extract attribute9 from the webauth response

<b>Attribute10</b>
Expression that would be evaluated to extract attribute10 from the webauth response

<b>Attribute11</b>
Expression that would be evaluated to extract attribute11 from the webauth response

<b>Attribute12</b>
Expression that would be evaluated to extract attribute12 from the webauth response

<b>Attribute13</b>
Expression that would be evaluated to extract attribute13 from the webauth response

<b>Attribute14</b>
Expression that would be evaluated to extract attribute14 from the webauth response

<b>Attribute15</b>
Expression that would be evaluated to extract attribute15 from the webauth response

<b>Attribute16</b>
Expression that would be evaluated to extract attribute16 from the webauth response

<b>devno</b>

<b>count</b>



##Example

show authentication webAuthAction a1

