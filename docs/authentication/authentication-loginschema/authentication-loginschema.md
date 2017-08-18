#authentication loginSchema

The following operations can be performed on "authentication loginSchema":


[add](#add-authentication-loginschema) | [rm](#rm-authentication-loginschema) | [set](#set-authentication-loginschema) | [unset](#unset-authentication-loginschema) | [show](#show-authentication-loginschema)

##add authentication loginSchema

Creates a LoginSchema. This profile is used to send authentication requirements to the UI tier for login


##Synopsys

add authentication loginSchema &lt;name> -authenticationSchema &lt;string> [-userExpression &lt;string>] [-passwdExpression &lt;string>] [-userCredentialIndex &lt;positive_integer>] [-passwordCredentialIndex &lt;positive_integer>] [-authenticationStrength &lt;positive_integer>] [-SSOCredentials ( YES | NO )]


##Arguments

<b>name</b>
Name for the new login schema. Login schema defines the way login form is rendered. It provides a way to customize the fields that are shown to the user. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after an action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').

<b>authenticationSchema</b>
Name of the file for reading authentication schema to be sent for Login Page UI. This file should contain xml definition of elements as per Citrix Forms Authentication Protocol to be able to render login form. If administrator does not want to prompt users for additional credentials but continue with previously obtained credentials, then "noschema" can be given as argument. Please note that this applies only to loginSchemas that are used with user-defined factors, and not the vserver factor.

<b>userExpression</b>
Expression for username extraction during login. This can be any relevant advanced policy expression.

<b>passwdExpression</b>
Expression for password extraction during login. This can be any relevant advanced policy expression.

<b>userCredentialIndex</b>
The index at which user entered username should be stored in session.
Minimum value: 1
Maximum value: 16

<b>passwordCredentialIndex</b>
The index at which user entered password should be stored in session.
Minimum value: 1
Maximum value: 16

<b>authenticationStrength</b>
Weight of the current authentication
Minimum value: 0
Maximum value: 65535

<b>SSOCredentials</b>
This option indicates whether current factor credentials are the default SSO (SingleSignOn) credentials.
Possible values: YES, NO
Default value: NO



##rm authentication loginSchema

Deletes an existing LoginSchema.


##Synopsys

rm authentication loginSchema &lt;name>


##Arguments

<b>name</b>
Name for the new login schema. Login schema defines the way login form is rendered. It provides a way to customize the fields that are shown to the user. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after an action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').



##set authentication loginSchema

Modifies the specified attributes of a LoginSchema.


##Synopsys

set authentication loginSchema &lt;name> [-authenticationSchema &lt;string>] [-userExpression &lt;string>] [-passwdExpression &lt;string>] [-userCredentialIndex &lt;positive_integer>] [-passwordCredentialIndex &lt;positive_integer>] [-authenticationStrength &lt;positive_integer>] [-SSOCredentials ( YES | NO )]


##Arguments

<b>name</b>
Name for the new login schema. Login schema defines the way login form is rendered. It provides a way to customize the fields that are shown to the user. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after an action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').

<b>authenticationSchema</b>
Name of the file for reading authentication schema to be sent for Login Page UI. This file should contain xml definition of elements as per Citrix Forms Authentication Protocol to be able to render login form. If administrator does not want to prompt users for additional credentials but continue with previously obtained credentials, then "noschema" can be given as argument. Please note that this applies only to loginSchemas that are used with user-defined factors, and not the vserver factor.

<b>userExpression</b>
Expression for username extraction during login. This can be any relevant advanced policy expression.

<b>passwdExpression</b>
Expression for password extraction during login. This can be any relevant advanced policy expression.

<b>userCredentialIndex</b>
The index at which user entered username should be stored in session.
Minimum value: 1
Maximum value: 16

<b>passwordCredentialIndex</b>
The index at which user entered password should be stored in session.
Minimum value: 1
Maximum value: 16

<b>authenticationStrength</b>
Weight of the current authentication
Minimum value: 0
Maximum value: 65535

<b>SSOCredentials</b>
This option indicates whether current factor credentials are the default SSO (SingleSignOn) credentials.
Possible values: YES, NO
Default value: NO



##unset authentication loginSchema

Use this command to remove authentication loginSchema settings.Refer to the set authentication loginSchema command for meanings of the arguments.


##Synopsys

unset authentication loginSchema &lt;name> [-userExpression] [-passwdExpression] [-userCredentialIndex] [-passwordCredentialIndex] [-authenticationStrength] [-SSOCredentials]


##show authentication loginSchema

Displays information about all configured login schema, or displays detailed information about the specified schema.


##Synopsys

show authentication loginSchema [&lt;name>]


##Arguments

<b>name</b>
Name for the new login schema. Login schema defines the way login form is rendered. It provides a way to customize the fields that are shown to the user. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after an action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').



##Outputs

<b>authenticationSchema</b>
Name of the file for reading authentication schema to be sent for Login Page UI. This file should contain xml definition of elements as per Citrix Forms Authentication Protocol to be able to render login form. If administrator does not want to prompt users for additional credentials but continue with previously obtained credentials, then "noschema" can be given as argument. Please note that this applies only to loginSchemas that are used with user-defined factors, and not the vserver factor.

<b>userExpression</b>
Expression for username extraction during login. This can be any relevant advanced policy expression.

<b>passwdExpression</b>
Expression for password extraction during login. This can be any relevant advanced policy expression.

<b>userCredentialIndex</b>
The index at which user entered username should be stored in session.

<b>passwordCredentialIndex</b>
The index at which user entered password should be stored in session.

<b>authenticationStrength</b>
Weight of the current authentication

<b>SSOCredentials</b>
This option indicates whether current factor credentials are the default SSO (SingleSignOn) credentials.

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



