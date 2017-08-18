#authentication OAuthAction

The following operations can be performed on "authentication OAuthAction":


[add](#add-authentication-oauthaction) | [rm](#rm-authentication-oauthaction) | [set](#set-authentication-oauthaction) | [unset](#unset-authentication-oauthaction) | [show](#show-authentication-oauthaction)

##add authentication OAuthAction

Adds an action to be used for OAuth authentication.


##Synopsys

add authentication OAuthAction &lt;name> [-OAuthType ( GENERIC | INTUNE )] [-authorizationEndpoint &lt;URL>] [-tokenEndpoint &lt;URL>] [-idtokenDecryptEndpoint &lt;URL>] -clientID &lt;string> -clientSecret  [-defaultAuthenticationGroup &lt;string>] [-Attribute1 &lt;string>] [-Attribute2 &lt;string>] [-Attribute3 &lt;string>] [-Attribute4 &lt;string>] [-Attribute5 &lt;string>] [-Attribute6 &lt;string>] [-Attribute7 &lt;string>] [-Attribute8 &lt;string>] [-Attribute9 &lt;string>] [-Attribute10 &lt;string>] [-Attribute11 &lt;string>] [-Attribute12 &lt;string>] [-Attribute13 &lt;string>] [-Attribute14 &lt;string>] [-Attribute15 &lt;string>] [-Attribute16 &lt;string>] [-tenantID &lt;string>] [-GraphEndpoint &lt;string>] [-refreshInterval &lt;positive_integer>] [-CertEndpoint &lt;string>] [-audience &lt;string>] [-userNameField &lt;string>] [-skewTime &lt;mins>] [-issuer &lt;string>]


##Arguments

<b>name</b>
Name for the OAuth Authentication action. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the profile is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my authentication action" or 'my authentication action').

<b>OAuthType</b>
Type of the OAuth implementation. Default value is generic implementation that is applicable for most deployments.
Possible values: GENERIC, INTUNE
Default value: GENERIC

<b>authorizationEndpoint</b>
Authorization endpoint/url to which unauthenticated user will be redirected. Netscaler appliance redirects user to this endpoint by adding query parameters including clientid. If this parameter not specified then as default value we take Token Endpoint/URL value. Please note that Authorization Endpoint or Token Endpoint is mandatory for oauthAction

<b>tokenEndpoint</b>
URL to which OAuth token will be posted to verify its authenticity. User obtains this token from Authorization server upon successful authentication. Netscaler appliance will validate presented token by posting it to the URL configured

<b>idtokenDecryptEndpoint</b>
URL to which obtained idtoken will be posted to get a decrypted user identity. Encrypted idtoken will be obtained by posting OAuth token to token endpoint. In order to decrypt idtoken, Netscaler appliance posts request to the URL configured

<b>clientID</b>
Unique identity of the client/user who is getting authenticated. Authorization server infers client configuration using this ID

<b>clientSecret</b>
Secret string established by user and authorization server

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.

<b>Attribute1</b>
Expression that would be evaluated to extract attribute1 from the oauth response

<b>Attribute2</b>
Expression that would be evaluated to extract attribute2 from the oauth response

<b>Attribute3</b>
Expression that would be evaluated to extract attribute3 from the oauth response

<b>Attribute4</b>
Expression that would be evaluated to extract attribute4 from the oauth response

<b>Attribute5</b>
Expression that would be evaluated to extract attribute5 from the oauth response

<b>Attribute6</b>
Expression that would be evaluated to extract attribute6 from the oauth response

<b>Attribute7</b>
Expression that would be evaluated to extract attribute7 from the oauth response

<b>Attribute8</b>
Expression that would be evaluated to extract attribute8 from the oauth response

<b>Attribute9</b>
Expression that would be evaluated to extract attribute9 from the oauth response

<b>Attribute10</b>
Expression that would be evaluated to extract attribute10 from the oauth response

<b>Attribute11</b>
Expression that would be evaluated to extract attribute11 from the oauth response

<b>Attribute12</b>
Expression that would be evaluated to extract attribute12 from the oauth response

<b>Attribute13</b>
Expression that would be evaluated to extract attribute13 from the oauth response

<b>Attribute14</b>
Expression that would be evaluated to extract attribute14 from the oauth response

<b>Attribute15</b>
Expression that would be evaluated to extract attribute15 from the oauth response

<b>Attribute16</b>
Expression that would be evaluated to extract attribute16 from the oauth response

<b>tenantID</b>
TenantID of the application. This is usually specific to providers such as Microsoft and usually refers to the deployment identifier.

<b>GraphEndpoint</b>
URL of the Graph API service to learn Enterprise Mobility Services (EMS) endpoints.

<b>refreshInterval</b>
Interval at which services are monitored for necessary configuration.
Default value: 1440
Minimum value: 0

<b>CertEndpoint</b>
URL of the endpoint that contains JWKs (Json Web Key) for JWT (Json Web Token) verification.

<b>audience</b>
Audience for which token sent by Authorization server is applicable. This is typically entity name or url that represents the recipient

<b>userNameField</b>
Attribute in the token from which username should be extracted.

<b>skewTime</b>
This option specifies the allowed clock skew in number of minutes that Netscaler allows on an incoming token. For example, if skewTime is 10, then token would be valid from (current time - 10) min to (current time + 10) min, ie 20min in all.
Default value: 5

<b>issuer</b>
Identity of the server whose tokens are to be accepted.



##Example

add authentication oauthAction a -authorizationEndpoint https://google.com/ -tokenEndpoint https://google.com/ -clientiD sadf -clientsecret df

##rm authentication OAuthAction

Removes a OAuth authentication action. You cannot remove an action that is used in any part of a policy.


##Synopsys

rm authentication OAuthAction &lt;name>


##Arguments

<b>name</b>
Name of the OAuth authentication action to remove.



##Example

rm authentication OAuthAction a1

##set authentication OAuthAction

Modifies the attributes of an existing OAuth authentication action.


##Synopsys

set authentication OAuthAction &lt;name> [-OAuthType ( GENERIC | INTUNE )] [-authorizationEndpoint &lt;URL>] [-tokenEndpoint &lt;URL>] [-idtokenDecryptEndpoint &lt;URL>] [-clientID &lt;string>] [-clientSecret ] [-defaultAuthenticationGroup &lt;string>] [-Attribute1 &lt;string>] [-Attribute2 &lt;string>] [-Attribute3 &lt;string>] [-Attribute4 &lt;string>] [-Attribute5 &lt;string>] [-Attribute6 &lt;string>] [-Attribute7 &lt;string>] [-Attribute8 &lt;string>] [-Attribute9 &lt;string>] [-Attribute10 &lt;string>] [-Attribute11 &lt;string>] [-Attribute12 &lt;string>] [-Attribute13 &lt;string>] [-Attribute14 &lt;string>] [-Attribute15 &lt;string>] [-Attribute16 &lt;string>] [-tenantID &lt;string>] [-GraphEndpoint &lt;string>] [-refreshInterval &lt;positive_integer>] [-CertEndpoint &lt;string>] [-audience &lt;string>] [-userNameField &lt;string>] [-skewTime &lt;mins>] [-issuer &lt;string>]


##Arguments

<b>name</b>
Name of the action to configure.

<b>OAuthType</b>
Type of the OAuth implementation. Default value is generic implementation that is applicable for most deployments.
Possible values: GENERIC, INTUNE
Default value: GENERIC

<b>authorizationEndpoint</b>
Authorization endpoint/url to which unauthenticated user will be redirected. Netscaler appliance redirects user to this endpoint by adding query parameters including clientid. If this parameter not specified then as default value we take Token Endpoint/URL value. Please note that Authorization Endpoint or Token Endpoint is mandatory for oauthAction

<b>tokenEndpoint</b>
URL to which OAuth token will be posted to verify its authenticity. User obtains this token from Authorization server upon successful authentication. Netscaler appliance will validate presented token by posting it to the URL configured

<b>idtokenDecryptEndpoint</b>
URL to which obtained idtoken will be posted to get a decrypted user identity. Encrypted idtoken will be obtained by posting OAuth token to token endpoint. In order to decrypt idtoken, Netscaler appliance posts request to the URL configured

<b>clientID</b>
Unique identity of the client/user who is getting authenticated. Authorization server infers client configuration using this ID

<b>clientSecret</b>
Secret string established by user and authorization server

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.

<b>Attribute1</b>
Expression that would be evaluated to extract attribute1 from the oauth response

<b>Attribute2</b>
Expression that would be evaluated to extract attribute2 from the oauth response

<b>Attribute3</b>
Expression that would be evaluated to extract attribute3 from the oauth response

<b>Attribute4</b>
Expression that would be evaluated to extract attribute4 from the oauth response

<b>Attribute5</b>
Expression that would be evaluated to extract attribute5 from the oauth response

<b>Attribute6</b>
Expression that would be evaluated to extract attribute6 from the oauth response

<b>Attribute7</b>
Expression that would be evaluated to extract attribute7 from the oauth response

<b>Attribute8</b>
Expression that would be evaluated to extract attribute8 from the oauth response

<b>Attribute9</b>
Expression that would be evaluated to extract attribute9 from the oauth response

<b>Attribute10</b>
Expression that would be evaluated to extract attribute10 from the oauth response

<b>Attribute11</b>
Expression that would be evaluated to extract attribute11 from the oauth response

<b>Attribute12</b>
Expression that would be evaluated to extract attribute12 from the oauth response

<b>Attribute13</b>
Expression that would be evaluated to extract attribute13 from the oauth response

<b>Attribute14</b>
Expression that would be evaluated to extract attribute14 from the oauth response

<b>Attribute15</b>
Expression that would be evaluated to extract attribute15 from the oauth response

<b>Attribute16</b>
Expression that would be evaluated to extract attribute16 from the oauth response

<b>tenantID</b>
TenantID of the application. This is usually specific to providers such as Microsoft and usually refers to the deployment identifier.

<b>GraphEndpoint</b>
URL of the Graph API service to learn Enterprise Mobility Services (EMS) endpoints.

<b>refreshInterval</b>
Interval at which services are monitored for necessary configuration.
Default value: 1440
Minimum value: 0

<b>CertEndpoint</b>
URL of the endpoint that contains JWKs (Json Web Key) for JWT (Json Web Token) verification.

<b>audience</b>
Audience for which token sent by Authorization server is applicable. This is typically entity name or url that represents the recipient

<b>userNameField</b>
Attribute in the token from which username should be extracted.

<b>skewTime</b>
This option specifies the allowed clock skew in number of minutes that Netscaler allows on an incoming token. For example, if skewTime is 10, then token would be valid from (current time - 10) min to (current time + 10) min, ie 20min in all.
Default value: 5

<b>issuer</b>
Identity of the server whose tokens are to be accepted.



##Example

set authentication OAuthAction a1 -ClientID someid123 -clientSecret somesecret

##unset authentication OAuthAction

Use this command to remove authentication OAuthAction settings.Refer to the set authentication OAuthAction command for meanings of the arguments.


##Synopsys

unset authentication OAuthAction &lt;name> [-OAuthType] [-idtokenDecryptEndpoint] [-defaultAuthenticationGroup] [-Attribute1] [-Attribute2] [-Attribute3] [-Attribute4] [-Attribute5] [-Attribute6] [-Attribute7] [-Attribute8] [-Attribute9] [-Attribute10] [-Attribute11] [-Attribute12] [-Attribute13] [-Attribute14] [-Attribute15] [-Attribute16] [-GraphEndpoint] [-refreshInterval] [-CertEndpoint] [-audience] [-userNameField] [-skewTime] [-issuer]


##show authentication OAuthAction

Displays information about the configured OAuth authentication action.


##Synopsys

show authentication OAuthAction [&lt;name>]


##Arguments

<b>name</b>
Name of the OAuth authentication action to display. If a name is not provided, information about all actions is shown.



##Outputs

<b>stateflag</b>

<b>authorizationEndpoint</b>
Authorization endpoint/url to which unauthenticated user will be redirected. Netscaler appliance redirects user to this endpoint by adding query parameters including clientid. If this parameter not specified then as default value we take Token Endpoint/URL value. Please note that Authorization Endpoint or Token Endpoint is mandatory for oauthAction

<b>tokenEndpoint</b>
URL to which OAuth token will be posted to verify its authenticity. User obtains this token from Authorization server upon successful authentication. Netscaler appliance will validate presented token by posting it to the URL configured

<b>idtokenDecryptEndpoint</b>
URL to which obtained idtoken will be posted to get a decrypted user identity. Encrypted idtoken will be obtained by posting OAuth token to token endpoint. In order to decrypt idtoken, Netscaler appliance posts request to the URL configured

<b>clientID</b>
Unique identity of the client/user who is getting authenticated. Authorization server infers client configuration using this ID

<b>clientSecret</b>
Secret string established by user and authorization server

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.

<b>Attribute1</b>
Expression that would be evaluated to extract attribute1 from the oauth response

<b>Attribute2</b>
Expression that would be evaluated to extract attribute2 from the oauth response

<b>Attribute3</b>
Expression that would be evaluated to extract attribute3 from the oauth response

<b>Attribute4</b>
Expression that would be evaluated to extract attribute4 from the oauth response

<b>Attribute5</b>
Expression that would be evaluated to extract attribute5 from the oauth response

<b>Attribute6</b>
Expression that would be evaluated to extract attribute6 from the oauth response

<b>Attribute7</b>
Expression that would be evaluated to extract attribute7 from the oauth response

<b>Attribute8</b>
Expression that would be evaluated to extract attribute8 from the oauth response

<b>Attribute9</b>
Expression that would be evaluated to extract attribute9 from the oauth response

<b>Attribute10</b>
Expression that would be evaluated to extract attribute10 from the oauth response

<b>Attribute11</b>
Expression that would be evaluated to extract attribute11 from the oauth response

<b>Attribute12</b>
Expression that would be evaluated to extract attribute12 from the oauth response

<b>Attribute13</b>
Expression that would be evaluated to extract attribute13 from the oauth response

<b>Attribute14</b>
Expression that would be evaluated to extract attribute14 from the oauth response

<b>Attribute15</b>
Expression that would be evaluated to extract attribute15 from the oauth response

<b>Attribute16</b>
Expression that would be evaluated to extract attribute16 from the oauth response

<b>tenantID</b>
TenantID of the application. This is usually specific to providers such as Microsoft and usually refers to the deployment identifier.

<b>GraphEndpoint</b>
URL of the Graph API service to learn Enterprise Mobility Services (EMS) endpoints.

<b>refreshInterval</b>
Interval at which services are monitored for necessary configuration.

<b>CertEndpoint</b>
URL of the endpoint that contains JWKs (Json Web Key) for JWT (Json Web Token) verification.

<b>OAuthType</b>
Type of the OAuth implementation. Default value is generic implementation that is applicable for most deployments.

<b>audience</b>
Audience for which token sent by Authorization server is applicable. This is typically entity name or url that represents the recipient

<b>userNameField</b>
Attribute in the token from which username should be extracted.

<b>skewTime</b>
This option specifies the allowed clock skew in number of minutes that Netscaler allows on an incoming token. For example, if skewTime is 10, then token would be valid from (current time - 10) min to (current time + 10) min, ie 20min in all.

<b>issuer</b>
Identity of the server whose tokens are to be accepted.

<b>OAuthStatus</b>
Describes status information of oauth server.

<b>devno</b>

<b>count</b>



##Example

show authentication OAuthAction a1

