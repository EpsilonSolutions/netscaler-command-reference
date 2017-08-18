#authentication storefrontAuthAction

The following operations can be performed on "authentication storefrontAuthAction":


[add](#add-authentication-storefrontauthaction) | [rm](#rm-authentication-storefrontauthaction) | [set](#set-authentication-storefrontauthaction) | [unset](#unset-authentication-storefrontauthaction) | [show](#show-authentication-storefrontauthaction)

##add authentication storefrontAuthAction

Adds an action to be used for authentication using storefront server.


##Synopsys

add authentication storefrontAuthAction &lt;name> -serverURL &lt;URL> [-domain &lt;string>] [-defaultAuthenticationGroup &lt;string>]


##Arguments

<b>name</b>
Name for the Storefront Authentication action. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the profile is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my authentication action" or 'my authentication action').

<b>serverURL</b>
URL of the Storefront server. This is the FQDN of the Storefront server. example: https://storefront.com/.  Authentication endpoints are learned dynamically by Gateway.

<b>domain</b>
Domain of the server that is used for authentication. If users enter name without domain, this parameter is added to username in the authentication request to server.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.



##Example

add authentication storefrontAuthAction a -serverurl https://google.com/

##rm authentication storefrontAuthAction

Removes a storefront authentication action. You cannot remove an action that is used in any part of a policy.


##Synopsys

rm authentication storefrontAuthAction &lt;name>


##Arguments

<b>name</b>
Name of the storefront authentication action to remove.



##Example

rm authentication storefrontAuthAction a1

##set authentication storefrontAuthAction

Modifies the attributes of an existing storefront authentication action.


##Synopsys

set authentication storefrontAuthAction &lt;name> [-serverURL &lt;URL>] [-domain &lt;string>] [-defaultAuthenticationGroup &lt;string>]


##Arguments

<b>name</b>
Name of the action to configure.

<b>serverURL</b>
URL of the Storefront server. This is the FQDN of the Storefront server. example: https://storefront.com/.  Authentication endpoints are learned dynamically by Gateway.

<b>domain</b>
Domain of the server that is used for authentication. If users enter name without domain, this parameter is added to username in the authentication request to server.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.



##Example

set authentication storefrontAuthAction a1 -serverurl someurl

##unset authentication storefrontAuthAction

Use this command to remove authentication storefrontAuthAction settings.Refer to the set authentication storefrontAuthAction command for meanings of the arguments.


##Synopsys

unset authentication storefrontAuthAction &lt;name> [-domain] [-defaultAuthenticationGroup]


##show authentication storefrontAuthAction

Displays information about the configured storefront authentication action.


##Synopsys

show authentication storefrontAuthAction [&lt;name>]


##Arguments

<b>name</b>
Name of the storefront authentication action to display. If a name is not provided, information about all actions is shown.



##Outputs

<b>stateflag</b>

<b>serverURL</b>
URL of the Storefront server. This is the FQDN of the Storefront server. example: https://storefront.com/.  Authentication endpoints are learned dynamically by Gateway.

<b>domain</b>
Domain of the server that is used for authentication. If users enter name without domain, this parameter is added to username in the authentication request to server.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.

<b>Success</b>

<b>Failure</b>

<b>devno</b>

<b>count</b>



##Example

show authentication storefrontAuthAction a1

