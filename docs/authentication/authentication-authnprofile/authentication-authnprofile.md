#authentication authnProfile

The following operations can be performed on "authentication authnProfile":


[add](#add-authentication-authnprofile) | [rm](#rm-authentication-authnprofile) | [set](#set-authentication-authnprofile) | [unset](#unset-authentication-authnprofile) | [show](#show-authentication-authnprofile)

##add authentication authnProfile

Creates an authentication profile to hold all authentication related configuration for TM vserver.


##Synopsys

add authentication authnProfile &lt;name> {-authnVsName &lt;string>} {-AuthenticationHost &lt;string>} {-AuthenticationDomain &lt;string>} [-AuthenticationLevel &lt;positive_integer>]


##Arguments

<b>name</b>
Name for the authentication profile. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the RADIUS action is added.

<b>authnVsName</b>
Name of the authentication vserver at which authentication should be done.
Maximum value: 128

<b>AuthenticationHost</b>
Hostname of the authentication vserver.
Maximum value: 256

<b>AuthenticationDomain</b>
Domain for which TM cookie must to be set. If unspecified, cookie will be set for FQDN.
Maximum value: 256

<b>AuthenticationLevel</b>
Authentication weight or level of the vserver to which this will bound. This is used to order TM vservers based on the protection required. A session that is created by authenticating against TM vserver at given level cannot be used to access TM vserver at a higher level.
Minimum value: 0
Maximum value: 255



##rm authentication authnProfile

Removes an authentication profile. A profile cannot be removed as long as it is set to a vserver.


##Synopsys

rm authentication authnProfile &lt;name>


##Arguments

<b>name</b>
Name of the authentication profile to be removed.



##set authentication authnProfile

Configures an authentication profile.


##Synopsys

set authentication authnProfile &lt;name> [-authnVsName &lt;string>] [-AuthenticationHost &lt;string>] [-AuthenticationDomain &lt;string>] [-AuthenticationLevel &lt;positive_integer>]


##Arguments

<b>name</b>
Name of the authentication profile.

<b>authnVsName</b>
Name of the authentication vserver at which authentication should be done.
Maximum value: 128

<b>AuthenticationHost</b>
Hostname of the authentication vserver.
Maximum value: 256

<b>AuthenticationDomain</b>
Domain for which TM cookie must to be set. If unspecified, cookie will be set for FQDN.
Maximum value: 256

<b>AuthenticationLevel</b>
Authentication weight or level of the vserver to which this will bound. This is used to order TM vservers based on the protection required. A session that is created by authenticating against TM vserver at given level cannot be used to access TM vserver at a higher level.
Minimum value: 0
Maximum value: 255



##unset authentication authnProfile

Use this command to remove authentication authnProfile settings.Refer to the set authentication authnProfile command for meanings of the arguments.


##Synopsys

unset authentication authnProfile &lt;name> [-AuthenticationDomain] [-AuthenticationLevel]


##show authentication authnProfile

Displays the current configuration for the authentication profile specified


##Synopsys

show authentication authnProfile [&lt;name>]


##Arguments

<b>name</b>
Name of the authentication profile.



##Outputs

<b>authnVsName</b>
Name of the authentication vserver at which authentication should be done.

<b>AuthenticationHost</b>
Hostname of the authentication vserver.

<b>AuthenticationDomain</b>
Domain for which TM cookie must to be set. If unspecified, cookie will be set for FQDN.

<b>AuthenticationLevel</b>
Authentication weight or level of the vserver to which this will bound. This is used to order TM vservers based on the protection required. A session that is created by authenticating against TM vserver at given level cannot be used to access TM vserver at a higher level.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



