#policy httpCallout

The following operations can be performed on "policy httpCallout":


[add](#add-policy-httpcallout) | [rm](#rm-policy-httpcallout) | [set](#set-policy-httpcallout) | [unset](#unset-policy-httpcallout) | [show](#show-policy-httpcallout)

##add policy httpCallout

Adds a default syntax expression element that, when evaluated, sends an HTTP request to a specified service and receives an HTTP response from the service. Can be used to obtain additional information for use in evaluating policy rules and other expressions. The expression prefix SYS.HTTP_CALLOUT invokes an HTTP callout. You can construct the HTTP callout request in one of two ways:* Specify individual parts of the request by using the HTTP method, host expression, URL stem expression, and header parameters. These parts are evaluated at run time and concatenated to build the request. * Specify the entire HTTP request in a single expression.


##Synopsys

add policy httpCallout &lt;name> [-IPAddress &lt;ip_addr|ipv6_addr>] [-port &lt;port>] [-vServer &lt;string>] [-returnType &lt;returnType>] [-httpMethod ( GET | POST )] [-hostExpr &lt;string>] [-urlStemExpr &lt;string>] [-headers &lt;name(value)> ...] [-parameters &lt;name(value)> ...] [-bodyExpr &lt;string>] [-fullReqExpr &lt;string>] [-scheme ( http | https )] [-resultExpr &lt;string>] [-cacheForSecs &lt;secs>] [-comment &lt;string>]


##Arguments

<b>name</b>
Name for the HTTP callout. Not case sensitive. Must begin with an ASCII letter or underscore (_) character, and must consist only of ASCII alphanumeric or underscore characters. Must not begin with 're' or 'xp' or be a word reserved for use as a default syntax expression qualifier prefix (such as HTTP) or enumeration value (such as ASCII). Must not be the name of an existing named expression, pattern set, dataset, stringmap, or HTTP callout.

<b>IPAddress</b>
IP Address of the server (callout agent) to which the callout is sent. Can be an IPv4 or IPv6 address.
Mutually exclusive with the Virtual Server parameter. Therefore, you cannot set the &lt;IP Address, Port&gt; and the Virtual Server in the same HTTP callout.

<b>port</b>
Server port to which the HTTP callout agent is mapped. Mutually exclusive with the Virtual Server parameter. Therefore, you cannot set the &lt;IP Address, Port&gt; and the Virtual Server in the same HTTP callout.
Minimum value: 1

<b>vServer</b>
Name of the load balancing, content switching, or cache redirection virtual server (the callout agent) to which the HTTP callout is sent. The service type of the virtual server must be HTTP. Mutually exclusive with the IP address and port parameters. Therefore, you cannot set the &lt;IP Address, Port&gt; and the Virtual Server in the same HTTP callout.

<b>returnType</b>
Type of data that the target callout agent returns in response to the callout. 
Available settings function as follows:
* TEXT - Treat the returned value as a text string. 
* NUM - Treat the returned value as a number.
* BOOL - Treat the returned value as a Boolean value. 
Note: You cannot change the return type after it is set.
Possible values: BOOL, NUM, TEXT

<b>httpMethod</b>
Method used in the HTTP request that this callout sends.  Mutually exclusive with the full HTTP request expression.
Possible values: GET, POST

<b>hostExpr</b>
Default Syntax string expression to configure the Host header. Can contain a literal value (for example, 10.101.10.11) or a derived value (for example, http.req.header("Host")). The literal value can be an IP address or a fully qualified domain name. Mutually exclusive with the full HTTP request expression.

<b>urlStemExpr</b>
Default Syntax string expression for generating the URL stem. Can contain a literal string (for example, "/mysite/index.html") or an expression that derives the value (for example, http.req.url). Mutually exclusive with the full HTTP request expression.

<b>headers</b>
One or more headers to insert into the HTTP request. Each header is specified as "name(expr)", where expr is a default syntax expression that is evaluated at runtime to provide the value for the named header. You can configure a maximum of eight headers for an HTTP callout. Mutually exclusive with the full HTTP request expression.

<b>parameters</b>
One or more query parameters to insert into the HTTP request URL (for a GET request) or into the request body (for a POST request). Each parameter is specified as "name(expr)", where expr is an default syntax expression that is evaluated at run time to provide the value for the named parameter (name=value). The parameter values are URL encoded. Mutually exclusive with the full HTTP request expression.

<b>bodyExpr</b>
An advanced string expression for generating the body of the request. The expression can contain a literal string or an expression that derives the value (for example, client.ip.src). Mutually exclusive with -fullReqExpr.

<b>fullReqExpr</b>
Exact HTTP request, in the form of a default syntax expression, which the NetScaler appliance sends to the callout agent. If you set this parameter, you must not include HTTP method, host expression, URL stem expression, headers, or parameters.
The request expression is constrained by the feature for which the callout is used. For example, an HTTP.RES expression cannot be used in a request-time policy bank or in a TCP content switching policy bank.
The NetScaler appliance does not check the validity of this request. You must manually validate the request.

<b>scheme</b>
Type of scheme for the callout server.
Possible values: http, https

<b>resultExpr</b>
Expression that extracts the callout results from the response sent by the HTTP callout agent. Must be a response based expression, that is, it must begin with HTTP.RES. The operations in this expression must match the return type. For example, if you configure a return type of TEXT, the result expression must be a text based expression. If the return type is NUM, the result expression (resultExpr) must return a numeric value, as in the following example: http.res.body(10000).length.

<b>cacheForSecs</b>
Duration, in seconds, for which the callout response is cached. The cached responses are stored in an integrated caching content group named "calloutContentGroup". If no duration is configured, the callout responses will not be cached unless normal caching configuration is used to cache them. This parameter takes precedence over any normal caching configuration that would otherwise apply to these responses.
	   Note that the calloutContentGroup definition may not be modified or removed nor may it be used with other cache policies.
Minimum value: 1
Maximum value: 31536000

<b>comment</b>
Any comments to preserve information about this HTTP callout.



##Example

add policy httpcallout h1 -IPAddress 1.1.1.1 -PORT 80

##rm policy httpCallout

Removes an HTTP callout. You cannot remove an HTTP callout that is used in any part of policy, action, or expression.


##Synopsys

rm policy httpCallout &lt;name>


##Arguments

<b>name</b>
Name of the HTTP callout to remove.



##Example

rm policy httpcallout h1

##set policy httpCallout

Modifies the attributes of an existing HTTP callout element.


##Synopsys

set policy httpCallout &lt;name> [-IPAddress &lt;ip_addr|ipv6_addr>] [-port &lt;port>] [-vServer &lt;string>] [-returnType &lt;returnType>] [-httpMethod ( GET | POST )] [-hostExpr &lt;string>] [-urlStemExpr &lt;string>] [-headers &lt;name(value)> ...] [-parameters &lt;name(value)> ...] [-bodyExpr &lt;string>] [-fullReqExpr &lt;string>] [-scheme ( http | https )] [-resultExpr &lt;string>] [-cacheForSecs &lt;secs>] [-comment &lt;string>]


##Arguments

<b>name</b>
Name of the HTTP callout to configure.

<b>IPAddress</b>
IP Address of the server (callout agent) to which the callout is sent. Can be an IPv4 or IPv6 address.
Mutually exclusive with the Virtual Server parameter. Therefore, you cannot set the &lt;IP Address, Port&gt; and the Virtual Server in the same HTTP callout.

<b>port</b>
Server port to which the HTTP callout agent is mapped. Mutually exclusive with the Virtual Server parameter. Therefore, you cannot set the &lt;IP Address, Port&gt; and the Virtual Server in the same HTTP callout.
Minimum value: 1

<b>vServer</b>
Name of the load balancing, content switching, or cache redirection virtual server (the callout agent) to which the HTTP callout is sent. The service type of the virtual server must be HTTP. Mutually exclusive with the IP address and port parameters. Therefore, you cannot set the &lt;IP Address, Port&gt; and the Virtual Server in the same HTTP callout.

<b>returnType</b>
Type of data that the target callout agent returns in response to the callout. 
Available settings function as follows:
* TEXT - Treat the returned value as a text string. 
* NUM - Treat the returned value as a number.
* BOOL - Treat the returned value as a Boolean value. 
Note: You cannot change the return type after it is set.
Possible values: BOOL, NUM, TEXT

<b>httpMethod</b>
Method used in the HTTP request that this callout sends.  Mutually exclusive with the full HTTP request expression.
Possible values: GET, POST

<b>hostExpr</b>
Default Syntax string expression to configure the Host header. Can contain a literal value (for example, 10.101.10.11) or a derived value (for example, http.req.header("Host")). The literal value can be an IP address or a fully qualified domain name. Mutually exclusive with the full HTTP request expression.

<b>urlStemExpr</b>
Default Syntax string expression for generating the URL stem. Can contain a literal string (for example, "/mysite/index.html") or an expression that derives the value (for example, http.req.url). Mutually exclusive with the full HTTP request expression.

<b>headers</b>
One or more headers to insert into the HTTP request. Each header is specified as "name(expr)", where expr is a default syntax expression that is evaluated at runtime to provide the value for the named header. You can configure a maximum of eight headers for an HTTP callout. Mutually exclusive with the full HTTP request expression.

<b>parameters</b>
One or more query parameters to insert into the HTTP request URL (for a GET request) or into the request body (for a POST request). Each parameter is specified as "name(expr)", where expr is an default syntax expression that is evaluated at run time to provide the value for the named parameter (name=value). The parameter values are URL encoded. Mutually exclusive with the full HTTP request expression.

<b>bodyExpr</b>
An advanced string expression for generating the body of the request. The expression can contain a literal string or an expression that derives the value (for example, client.ip.src). Mutually exclusive with -fullReqExpr.

<b>fullReqExpr</b>
Exact HTTP request, in the form of a default syntax expression, which the NetScaler appliance sends to the callout agent. If you set this parameter, you must not include HTTP method, host expression, URL stem expression, headers, or parameters.
The request expression is constrained by the feature for which the callout is used. For example, an HTTP.RES expression cannot be used in a request-time policy bank or in a TCP content switching policy bank.
The NetScaler appliance does not check the validity of this request. You must manually validate the request.

<b>scheme</b>
Type of scheme for the callout server.
Possible values: http, https

<b>resultExpr</b>
Expression that extracts the callout results from the response sent by the HTTP callout agent. Must be a response based expression, that is, it must begin with HTTP.RES. The operations in this expression must match the return type. For example, if you configure a return type of TEXT, the result expression must be a text based expression. If the return type is NUM, the result expression (resultExpr) must return a numeric value, as in the following example: http.res.body(10000).length.

<b>cacheForSecs</b>
Duration, in seconds, for which the callout response is cached. The cached responses are stored in an integrated caching content group named "calloutContentGroup". If no duration is configured, the callout responses will not be cached unless normal caching configuration is used to cache them. This parameter takes precedence over any normal caching configuration that would otherwise apply to these responses.
	   Note that the calloutContentGroup definition may not be modified or removed nor may it be used with other cache policies.
Minimum value: 1
Maximum value: 31536000

<b>comment</b>
Any comments to preserve information about this HTTP callout.



##Example

set policy httpcallout h1 -IPAddress 1.1.1.1 -PORT 80

##unset policy httpCallout

Use this command to remove policy httpCallout settings.Refer to the set policy httpCallout command for meanings of the arguments.


##Synopsys

unset policy httpCallout &lt;name> [-IPAddress] [-port] [-vServer] [-httpMethod] [-hostExpr] [-urlStemExpr] [-headers] [-parameters] [-bodyExpr] [-fullReqExpr] [-resultExpr] [-cacheForSecs] [-comment]


##show policy httpCallout

Displays information about the configured HTTP callouts.


##Synopsys

show policy httpCallout [&lt;name>]


##Arguments

<b>name</b>
Name of the HTTP callout to display. If a name is not provided, information about all configured HTTP callouts is shown.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>IPAddress</b>
Server IP address.

<b>port</b>
Server port.

<b>vServer</b>
Vserver name

<b>returnType</b>
Return type of the http callout

<b>scheme</b>
Type of scheme(HTTP/HTTPS) for the callout server

<b>httpMethod</b>
Http callout request type

<b>hostExpr</b>
PI string expression for Host

<b>urlStemExpr</b>
PI string expression for URL stem

<b>headers</b>
PI string expression for request http headers

<b>parameters</b>
PI string expression for request query parameters

<b>fullReqExpr</b>
PI string expression for full http callout request

<b>resultExpr</b>
PI string expression for http callout response

<b>hits</b>
Total hits

<b>undefHits</b>
Total undefs

<b>svrState</b>
The state of the service

<b>undefReason</b>
Reason for last undef

<b>recursiveCallout</b>
Number of recursive callouts

<b>bodyExpr</b>
An advanced string expression for generating the body of the request. The expression can contain a literal string or an expression that derives the value (for example, client.ip.src). Mutually exclusive with -fullReqExpr.

<b>cacheForSecs</b>
Duration, in seconds, for which the callout response is cached. The cached responses are stored in an integrated caching content group named "calloutContentGroup". If no duration is configured, the callout responses will not be cached unless normal caching configuration is used to cache them. This parameter takes precedence over any normal caching configuration that would otherwise apply to these responses.
	   Note that the calloutContentGroup definition may not be modified or removed nor may it be used with other cache policies.

<b>comment</b>
Any comments to preserve information about this HTTP callout.

<b>devno</b>

<b>count</b>



##Example

show policy httpcallout h1

