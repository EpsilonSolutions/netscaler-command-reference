#authentication dfaAction

The following operations can be performed on "authentication dfaAction":


[add](#add-authentication-dfaaction) | [rm](#rm-authentication-dfaaction) | [set](#set-authentication-dfaaction) | [unset](#unset-authentication-dfaaction) | [show](#show-authentication-dfaaction)

##add authentication dfaAction

Creates an action (profile) for a DFA server. The profile contains all configuration data necessary to communicate with that DFA server.


##Synopsys

add authentication dfaAction &lt;name> {-clientID &lt;string>} {-serverURL &lt;URL>} {-passPhrase } [-defaultAuthenticationGroup &lt;string>]


##Arguments

<b>name</b>
Name for the DFA action. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the DFA action is added.

<b>clientID</b>
If configured, this string is sent to the DFA server as the X-Citrix-Exchange header value.

<b>serverURL</b>
DFA Server URL

<b>passPhrase</b>
Key shared between the DFA server and the NetScaler appliance. 
Required to allow the NetScaler appliance to communicate with the DFA server.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.



##rm authentication dfaAction

Removes a DFA profile (action). An action cannot be removed as long as it is bound to a policy.


##Synopsys

rm authentication dfaAction &lt;name>


##Arguments

<b>name</b>
Name of the action to be removed.



##set authentication dfaAction

Configures a DFA server profile (action). The profile contains all configuration data needed to communicate with that DFA server.


##Synopsys

set authentication dfaAction &lt;name> [-clientID &lt;string>] [-serverURL &lt;URL>] {-passPhrase } [-defaultAuthenticationGroup &lt;string>]


##Arguments

<b>name</b>
Name of the RADIUS profile.

<b>clientID</b>
If configured, this string is sent to the DFA server as the X-Citrix-Exchange header value.

<b>serverURL</b>
DFA Server URL

<b>passPhrase</b>
Key shared between the DFA server and the NetScaler appliance. 
Required to allow the NetScaler appliance to communicate with the DFA server.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.



##unset authentication dfaAction

Use this command to remove authentication dfaAction settings.Refer to the set authentication dfaAction command for meanings of the arguments.


##Synopsys

unset authentication dfaAction &lt;name> [-clientID] [-serverURL] [-defaultAuthenticationGroup]


##show authentication dfaAction

Displays the current configuration settings for the specified DFA profile (action).


##Synopsys

show authentication dfaAction [&lt;name>]


##Arguments

<b>name</b>
Name of the DFA profile.



##Outputs

<b>passPhrase</b>
Key shared between the DFA server and the NetScaler appliance. 
Required to allow the NetScaler appliance to communicate with the DFA server.

<b>clientID</b>
If configured, this string is sent to the DFA server as the X-Citrix-Exchange header value.

<b>serverURL</b>
DFA Server URL

<b>Success</b>

<b>Failure</b>

<b>stateflag</b>

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.

<b>devno</b>

<b>count</b>



