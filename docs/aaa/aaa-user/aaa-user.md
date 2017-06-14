#aaa user

The following operations can be performed on "aaa user":


[add](#add-aaa-user) | [rm](#rm-aaa-user) | [set](#set-aaa-user) | [bind](#bind-aaa-user) | [unbind](#unbind-aaa-user) | [show](#show-aaa-user) | [unlock](#unlock-aaa-user)

##add aaa user

Adds a local AAA user account and verifies the configuration to ensure that it is correct.


##Synopsys

add aaa user &lt;userName> {-password }


##Arguments

<b>userName</b>
Name for the user. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the user is added. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my aaa user" or "my aaa user").

<b>password</b>
Password with which the user logs on. Required for any user account that does not exist on an external authentication server. If you are not using an external authentication server, all user accounts must have a password. If you are using an external authentication server, you must provide a password for local user accounts that do not exist on the authentication server.



##Example

add aaa user johndoe -password abcd add aaa user johndoe -password The above example adds user johndoe with password abcd for first case, password supplied on prompt for second case

##rm aaa user

Removes a local AAA user account and the associated configuration.


##Synopsys

rm aaa user &lt;userName>


##Arguments

<b>userName</b>
Name of the AAA user account to remove.



##set aaa user

Configures the password for an existing local AAA user account. This command prompts you for a new password. NOTE: AAA does not request confirmation of the new password, so you might want to test the new password before sending it to the user.


##Synopsys

set aaa user &lt;userName>


##Arguments

<b>userName</b>
Name of the local AAA user account.

<b>password</b>
Password with which the user logs on. Required for any user account that does not exist on an external authentication server. If you are not using an external authentication server, all user accounts must have a password. If you are using an external authentication server, you must provide a password for local user accounts that do not exist on the authentication server.



##Example

set aaa user johndoe password abcd The above command sets the password for johndoe to abcd

##bind aaa user

Binds a policy to the specified user account.


##Synopsys

bind aaa user &lt;userName> [-policy &lt;string> [-priority &lt;positive_integer>]] [-intranetApplication &lt;string>] [-urlName &lt;string>] [-intranetIP &lt;ip_addr> [&lt;netmask>]]


##Arguments

<b>userName</b>
User account to which to bind the policy.

<b>policy</b>
Name for the policy that you are creating. Must begin with a letter, number, or the underscore character (_), and must consist only of letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore characters. Cannot be changed after the policy is added. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my policy" or "my policy").

<b>intranetApplication</b>
Name of the intranet VPN application to which the policy applies.

<b>urlName</b>
URL of the intranet application to which you are binding the policy.

<b>intranetIP</b>
IP address of the intranet application to which you are binding the policy.



##Example

To bind intranetip to the user joe: bind aaa user joe -intranetip 10.102.1.123

##unbind aaa user

Unbinds a policy from the specified user account.


##Synopsys

unbind aaa user &lt;userName> [-policy &lt;string>] [-intranetApplication &lt;string>] [-urlName &lt;string>] [-intranetIP &lt;ip_addr> [&lt;netmask>]]


##Arguments

<b>userName</b>
Name of the user account from which to unbind the policy.

<b>policy</b>
Name of the policy to unbind.

<b>intranetApplication</b>
Name of the intranet VPN application from which you are unbinding the policy.

<b>urlName</b>
URL of the intranet application from which you are unbinding the policy.

<b>intranetIP</b>
Intranet IP address of the application from which you are unbinding the policy.



##Example

unbind AAA user joe -intranetip 10.102.1.123

##show aaa user

Displays the current configuration of a AAA user account.


##Synopsys

show aaa user [&lt;userName>] [-loggedIn]


##Arguments

<b>userName</b>
Name of the user who has the account.

<b>loggedIn</b>
Show whether the user is logged in or not.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>groupName</b>
The group name

<b>policy</b>
The policy Name.

<b>priority</b>
The priority of the policy.

<b>intranetApplication</b>
Name of the intranet VPN application to which the policy applies.

<b>urlName</b>
The intranet url.

<b>actType</b>

<b>intranetIP</b>
The Intranet IP bound to the user

<b>netmask</b>
The netmask for the Intranet IP

<b>policySubType</b>

<b>stateflag</b>

<b>password</b>
Password with which the user logs on. Required for any user account that does not exist on an external authentication server. If you are not using an external authentication server, all user accounts must have a password. If you are using an external authentication server, you must provide a password for local user accounts that do not exist on the authentication server.

<b>devno</b>

<b>count</b>



##Example

Example &gt; show aaa user joe UserName: joe IntranetIP: 10.102.1.123 Bound to groups: GroupName: engg Done &gt;

##unlock aaa user

Unlocks a AAA user account which has been locked earlier for exceeding login attempts.


##Synopsys

unlock aaa user &lt;userName>


##Arguments

<b>userName</b>
Name of the AAA user account to unlock.



