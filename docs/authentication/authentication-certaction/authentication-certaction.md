#authentication certAction

The following operations can be performed on "authentication certAction":


[add](#add-authentication-certaction) | [rm](#rm-authentication-certaction) | [set](#set-authentication-certaction) | [unset](#unset-authentication-certaction) | [show](#show-authentication-certaction)

##add authentication certAction

Adds an action (profile) for a client certificate (cert) authentication server. The profile contains all configuration data necessary to communicate with that client cert authentication server.


##Synopsys

add authentication certAction &lt;name> [-twoFactor ( ON | OFF )] [-userNameField &lt;string>] [-groupNameField &lt;string>] [-defaultAuthenticationGroup &lt;string>]


##Arguments

<b>name</b>
Name for the client cert authentication server profile (action). 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after certifcate action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my authentication action" or 'my authentication action').

<b>twoFactor</b>
Enables or disables two-factor authentication. 
Two factor authentication is client cert authentication followed by password authentication.
Possible values: ON, OFF
Default value: OFF

<b>userNameField</b>
Client-cert field from which the username is extracted. Must be set to either ""Subject"" and ""Issuer"" (include both sets of double quotation marks).
Format: &lt;field&gt;:&lt;subfield&gt;.

<b>groupNameField</b>
Client-cert field from which the group is extracted.  Must be set to either ""Subject"" and ""Issuer"" (include both sets of double quotation marks).
Format: &lt;field&gt;:&lt;subfield&gt;

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.



##Example

add authentication certaction -twoFactor ON -userNameField "Subject:CN" -groupNameField "Subject:OU"

##Related Commands

<ul><li><a href="../../../ation-certpolicy.html#add-authentication-certp/ation-certpolicy.html#add-authentication-certp">add authentication certpolicy</a></li></ul>



##rm authentication certAction

Removes an existing client cert authentication server profile (action).


##Synopsys

rm authentication certAction &lt;name>


##Arguments

<b>name</b>
Name of the profile to be removed.



##set authentication certAction

Configures a client cert authentication server profile (action).


##Synopsys

set authentication certAction &lt;name> [-twoFactor ( ON | OFF )] [-userNameField &lt;string>] [-groupNameField &lt;string>] [-defaultAuthenticationGroup &lt;string>]


##Arguments

<b>name</b>
Name of the client cert server profile.

<b>twoFactor</b>
Enables or disables two-factor authentication. 
Two factor authentication is client cert authentication followed by password authentication.
Possible values: ON, OFF
Default value: OFF

<b>userNameField</b>
Client-cert field from which the username is extracted. Must be set to either ""Subject"" and ""Issuer"" (include both sets of double quotation marks).
Format: &lt;field&gt;:&lt;subfield&gt;.

<b>groupNameField</b>
Client-cert field from which the group is extracted.  Must be set to either ""Subject"" and ""Issuer"" (include both sets of double quotation marks).
Format: &lt;field&gt;:&lt;subfield&gt;

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.



##Example

set authentication certaction -twoFactor ON -userNameField "Subject:CN" -groupNameField "Subject:OU"

##Related Commands

<ul><li><a href="../../../ation-certpolicy.html#add-authentication-certp/ation-certpolicy.html#add-authentication-certp">add authentication certpolicy</a></li></ul>



##unset authentication certAction

Use this command to remove authentication certAction settings.Refer to the set authentication certAction command for meanings of the arguments.


##Synopsys

unset authentication certAction &lt;name> [-twoFactor] [-userNameField] [-groupNameField] [-defaultAuthenticationGroup]


##show authentication certAction

Displays the current configuration settings for the specified client cert authentication server profile (action).


##Synopsys

show authentication certAction [&lt;name>]


##Arguments

<b>name</b>
Name of the client cert server profile (action).



##Outputs

<b>twoFactor</b>
The state of two factor authentication.

<b>userNameField</b>
The field in the certificate from which the username will be extracted.

<b>groupNameField</b>
The field in the certificate from which the group will be extracted.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.

<b>stateflag</b>

<b>devno</b>

<b>count</b>



