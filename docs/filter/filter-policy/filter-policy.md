#filter policy

The following operations can be performed on "filter policy":


[add](#add-filter-policy) | [rm](#rm-filter-policy) | [set](#set-filter-policy) | [show](#show-filter-policy)

##add filter policy

Creates a content filtering policy.


##Synopsys

add filter policy &lt;name> -rule &lt;expression> (-reqAction &lt;string> | -resAction &lt;string>)


##Arguments

<b>name</b>
Name for the filtering action. Must begin with a letter, number, or the underscore character (_). Other characters allowed, after the first character, are the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), and colon (:) characters. Choose a name that helps identify the type of action. The name cannot be updated after the policy is created.
CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my policy" or 'my policy').

<b>rule</b>
NetScaler classic expression specifying the type of connections that match this policy.

<b>reqAction</b>
Name of the action to be performed on requests that match the policy. Cannot be specified if the rule includes condition to be evaluated for responses.

<b>resAction</b>
The action to be performed on the response. The string value can be a filter action created filter action or a built-in action.



##Example

Example 1:add policy expression e1 "sourceip == 66.33.22.0 -netmask 255.255.255.0"add policy expression e2 "URL == /admin/account.asp"add filter policy ip_filter -rule "e1 && e2"  -reqAction RESETAfter creating above filter policy, it can be activated by binding it globally:bind filter global ip_filterWith the configured ip_filter (name of the filter policy), the NetScaler system sends a TCP reset to all HTTP requests for the /admin/account.asp URL from 66.33.22.0 Class C network. This action is applied at the HTTP request time.Example 2:To silently drop (without sending FIN) all the HTTP requests in which the URL has root.exe or cmd.exe, below filter policy can be configured:add filter policy nimda_filter -rule "URL contains root.exe || URL contains cmd.exe" -reqAction DROPbind filter global nimda_filterExample 3:add filter policy url_filter -rule "url == /foo/secure.asp && SOURCEIP != 65.186.55.0 -netmask 255.255.255.0 && SOURCEIP != 65.202.35.0 -netmask 255.255.255.0" -reqaction RESETbind filter global url_filterWith the above configured filter policy named url_filter, the NetScaler system sends RESET to all HTTP requests for the URL /foo/secure.asp from all the networks except from 65.186.55.0 and 65.202.35.0 Class C networks. This action is applied at the HTTP request time.Note: In above examples, the RESET and DROP are built-in actions in the NetScaler system."show filter action" and "show filter policy" CLI commands show the configured filter actions and policies in NetScaler system respectively. "show filter global" command shows all the globallyactive filter policies.

##rm filter policy

Removes a filter policy.


##Synopsys

rm filter policy &lt;name>


##Arguments

<b>name</b>
Name of the filter policy to be removed.



##Example

rm filter policy filter_policy_nameThe "show filter policy" command shows all filter policies that are currently defined.

##set filter policy

Modifies a filter policy.


##Synopsys

set filter policy &lt;name> [-rule &lt;expression>] [-reqAction &lt;string> | -resAction &lt;string>]


##Arguments

<b>name</b>
Name of the filter policy to be modified.

<b>rule</b>
NetScaler classic expression specifying the type of connections that match this policy.

<b>reqAction</b>
Name of the action to be performed on requests that match the policy. Cannot be specified if the rule includes condition to be evaluated for responses.

<b>resAction</b>
The action to be performed on the response. The string value can be a filter action created filter action or a built-in action.



##Example

Example 1:A filter policy to allow access of URL /foo/secure.asp only from 65.186.55.0 network can be created using below command:add filter policy url_filter -rule "URL == /foo/secure.asp && SOURCEIP != 65.186.55.0 -netmask 255.255.255.0" -reqAction RESETThis policy is activated using:bind filter global url_filterLater, to allow access of this url from second network 65.202.35.0 too, above filter policy can be changed by issuing below command:set filter policy url_filter -rule "URL == /foo/secure.asp && SOURCEIP != 65.186.55.0 -netmask 255.255.255.0 && SOURCEIP != 65.202.35.0 -netmask 255.255.255.0"Changed filter policy can be viewed by using following command:show filter policy url_filter        Name: url_filter  Rule: (URL == /foo/secure.asp && (SOURCEIP != 65.186.55.0 -netmask 255.255.255.0 && SOURCEIP != 65.202.35.0 -netmask 255.255.255.0))        Request action: RESET        Response action:        Hits: 0 Done

##show filter policy

Displays information about the filter policies.


##Synopsys

show filter policy [&lt;name>]


##Arguments

<b>name</b>
Name of the filter policy to be displayed. If a name is not provided, information about all the filter policies is shown.



##Outputs

<b>rule</b>
NetScaler classic expression specifying the type of connections that match this policy.

<b>reqAction</b>
The name of the action to be performed on the request.

<b>resAction</b>
The action to be performed on the response.

<b>hits</b>

<b>boundTo</b>
The entity name to which policy is bound

<b>activePolicy</b>

<b>priority</b>

<b>bindPolicyType</b>

<b>policyType</b>

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show filter policy1)      Name: nimda_filter Rule: (URL CONTAINS root.exe || URL CONTAINS cmd.exe)        Request action: RESET        Response action:        Hits: 02)      Name: ip_filter Rule: (src_ips && URL == /admin/account.asp)        Request action: RESET        Response action:        Hits: 0 DoneIndividual filter policy can also be viewed by giving filter policy name as argument:show filter policy ip_filter        Name: ip_filter Rule: (src_ips && URL == /admin/account.asp)        Request action: RESET        Response action:        Hits: 0 Done

