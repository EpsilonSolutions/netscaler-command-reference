#wf site

The following operations can be performed on "wf site":


[add](#add-wf-site) | [rm](#rm-wf-site) | [set](#set-wf-site) | [show](#show-wf-site)

##add wf site

Creates a WebFront site on the NetScaler appliance.          The NetScaler WebFront feature provides access to Citrix XenApp and Citrix XenDesktop applications. Users access resources through a standard web browser or by using the Citrix Receiver plug-in.


##Synopsys

add wf site &lt;siteName> -storefronturl &lt;string> -storeName &lt;string> [-html5Receiver &lt;html5Receiver>] [-workspaceControl ( ON | OFF )] [-displayRoamingAccounts ( ON | OFF )] [-xframeOptions ( ALLOW | DENY )]


##Arguments

<b>siteName</b>
Name of the WebFront site being created on the NetScaler appliance.

<b>storefronturl</b>
FQDN or IP of Windows StoreFront server where the store is configured.

<b>storeName</b>
Name of the store present in StoreFront

<b>html5Receiver</b>
Specifies whether or not to use HTML5 receiver for launching apps for the WF site.
Possible values: ALWAYS, FALLBACK, OFF
Default value: FALLBACK

<b>workspaceControl</b>
Specifies whether of not to use workspace control for the WF site.
Possible values: ON, OFF
Default value: ON

<b>displayRoamingAccounts</b>
Specifies whether or not to display the accounts selection screen during First Time Use of Receiver 
Possible values: ON, OFF
Default value: ON

<b>xframeOptions</b>
The value to be sent in the X-Frame-Options header. WARNING: Setting this option to ALLOW could leave the end user vulnerable to Click Jacking attacks.
Possible values: ALLOW, DENY
Default value: DENY



##Example

add wf site site1 -storefrontURL http://storefront.domain.com -storeName store

##rm wf site

Removes a WebFront site from the NetScaler appliance.


##Synopsys

rm wf site &lt;siteName>


##Arguments

<b>siteName</b>
Name of the WebFront site being created on the NetScaler appliance.



##Example

rm wf site site1

##set wf site

Modifies the parameters of a WebFront site configured on the NetScaler appliance.


##Synopsys

set wf site &lt;siteName> [-storefronturl &lt;string>] [-storeName &lt;string>] [-html5Receiver &lt;html5Receiver>] [-workspaceControl ( ON | OFF )] [-displayRoamingAccounts ( ON | OFF )] [-xframeOptions ( ALLOW | DENY )]


##Arguments

<b>siteName</b>
Name of the WebFront site being created on the NetScaler appliance.

<b>storefronturl</b>
FQDN or IP of Windows StoreFront server where the store is configured.

<b>storeName</b>
Name of the store present in StoreFront

<b>html5Receiver</b>
Specifies whether or not to use HTML5 receiver for launching apps for the WF site.
Possible values: ALWAYS, FALLBACK, OFF
Default value: FALLBACK

<b>workspaceControl</b>
Specifies whether of not to use workspace control for the WF site.
Possible values: ON, OFF
Default value: ON

<b>displayRoamingAccounts</b>
Specifies whether or not to display the accounts selection screen during First Time Use of Receiver 
Possible values: ON, OFF
Default value: ON

<b>xframeOptions</b>
The value to be sent in the X-Frame-Options header. WARNING: Setting this option to ALLOW could leave the end user vulnerable to Click Jacking attacks.
Possible values: ALLOW, DENY
Default value: DENY



##Example

set wf site site1 -storefrontURL https://storefront.domain.com

##show wf site

Displays settings of all the WebFront sites, or of a specified site.  To display settings of all the WebFront sites, run the command without any parameters.


##Synopsys

show wf site [&lt;siteName>]


##Arguments

<b>siteName</b>
Path of a WebFront site whose details you want the NetScaler appliance to display.



##Outputs

<b>storefronturl</b>
FQDN or IP of Windows StoreFront server where the store is configured.

<b>storeName</b>
The Store Name

<b>html5Receiver</b>
Specifies whether or not to use HTML5 receiver for launching apps for the WF site.

<b>workspaceControl</b>
Specifies whether of not to use workspace control for the WF site.

<b>displayRoamingAccounts</b>
Specifies whether or not to display the accounts selection screen during First Time Use of Receiver

<b>xframeOptions</b>
The value to be sent in the X-Frame-Options header. WARNING: Setting this option to ALLOW could leave the end user vulnerable to Click Jacking attacks.

<b>state</b>
State of wf site

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show wf site

