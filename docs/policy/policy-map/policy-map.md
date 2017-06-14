#policy map

The following operations can be performed on "policy map":


[add](#add-policy-map) | [rm](#rm-policy-map) | [show](#show-policy-map)

##add policy map

Creates a policy to map a publicly known domain name to a target domain name for a reverse proxy virtual server used by the cache redirection feature. Optionally, you can also specify a source and target URL. The map policy can be associated with a reverse proxy cache redirection virtual server by using the 'bind cr vserver' command. There can be only one default map policy for a domain.


##Synopsys

add policy map &lt;mapPolicyName> -sd &lt;string> [-su &lt;string>] [-td &lt;string>] [-tu &lt;string>]


##Arguments

<b>mapPolicyName</b>
Name for the map policy. Must begin with a letter, number, or the underscore (_) character and must consist only of letters, numbers, and the hash (#), period (.), colon (:), space ( ), at (@), equals (=), hyphen (-), and underscore (_) characters.
CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my map" or 'my map').

<b>sd</b>
Publicly known source domain name. This is the domain name with which a client request arrives at a reverse proxy virtual server for cache redirection. If you specify a source domain, you must specify a target domain.

<b>su</b>
Source URL. Specify all or part of the source URL, in the following format: /[[prefix] [*]] [.suffix].

<b>td</b>
Target domain name sent to the server. The source domain name is replaced with this domain name.

<b>tu</b>
Target URL. Specify the target URL in the following format: /[[prefix] [*]][.suffix].



##Example

Example 1The following example creates a default map policy (map1) for the source domain www.a.com. Any client requests with this source domain in the host header is changed to www.real_a.com.add policy map map2 -sd www.a.com -td www.real.a.comExample 2This example shows how to create a URL map policy (map2) if you want to translate /sports.html in the incoming request to /news.html in addition to mapping the source domain www.a.com to www.real_a.com in the outgoing request.add policy map map2 -sd www.a.com-td www.real_a.com -su /sports.html-tu /news.htmlThese type of map policies, called "URL map policies," have the following restrictions:l	URL map policies belonging to www.a.com cannot be added without first adding a default map policy as described in Example 1.l	If a source suffix has been specified for URL map policy, a destination suffix must also be specified.l	If an exact URL has been specified as the source, then the target URL should also be exact URL.l	If there is a source prefix in the URL, there must be also a destination prefix in the URL.

##rm policy map

Removes a map policy. Before removing the map policy, you must unbind the map policy from the reverse proxy virtual server.


##Synopsys

rm policy map &lt;mapPolicyName>


##Arguments

<b>mapPolicyName</b>
Name of the policy map to remove.



##show policy map

Displays information about the available policy maps.


##Synopsys

show policy map [&lt;mapPolicyName>]


##Arguments

<b>mapPolicyName</b>
Name of the policy map to display. If a name is not provided, information of all configured policy maps is shown.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>sd</b>
Publicly known source domain name. This is the domain name with which a client request arrives at a reverse proxy virtual server for cache redirection. If you specify a source domain, you must specify a target domain.

<b>su</b>
The source URL.

<b>td</b>
The domain name sent to the server.

<b>tu</b>
The target URL.

<b>targetName</b>
The expression string.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



