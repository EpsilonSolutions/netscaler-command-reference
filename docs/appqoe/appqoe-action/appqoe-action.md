#appqoe action

The following operations can be performed on "appqoe action":


[add](#add-appqoe-action) | [rm](#rm-appqoe-action) | [set](#set-appqoe-action) | [unset](#unset-appqoe-action) | [show](#show-appqoe-action)

##add appqoe action

Add a new AppQoE action for triggering


##Synopsys

add appqoe action &lt;name> [-priority &lt;priority>] [-respondWith ( ACS | NS )  [&lt;CustomFile>]  [-altContentSvcName &lt;string>]  [-altContentPath &lt;string>]  [-maxConn &lt;positive_integer>]  [-delay &lt;usecs>]] [-polqDepth &lt;positive_integer>] [-priqDepth &lt;positive_integer>] [-dosTrigExpression &lt;expression>] [-dosAction ( SimpleResponse | HICResponse )] [-tcpprofile &lt;string>]


##Arguments

<b>name</b>
Name for the AppQoE action. Must begin with a letter, number, or the underscore symbol (_). Other characters allowed, after the first character, are the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), and colon (:) characters. This is a mandatory argument

<b>priority</b>
Priority for queuing the request. If server resources are not available for a request that matches the configured rule, this option specifies a priority for queuing the request until the server resources are available again. If priority is not configured then Lowest priority will be used to queue the request.
Possible values: HIGH, MEDIUM, LOW, LOWEST

<b>respondWith</b>
Responder action to be taken when the threshold is reached. Available settings function as follows:
            ACS - Serve content from an alternative content service
                  Threshold : maxConn or delay
            NS - Serve from the NetScaler appliance (built-in response)
                 Threshold : maxConn or delay
Possible values: ACS, NS

<b>CustomFile</b>
name of the HTML page object to use as the response

<b>altContentSvcName</b>
Name of the alternative content service to be used in the ACS

<b>altContentPath</b>
Path to the alternative content service to be used in the ACS

<b>polqDepth</b>
Policy queue depth threshold value. When the policy queue size (number of requests queued for the policy binding this action is attached to) increases to the specified polqDepth value, subsequent requests are dropped to the lowest priority level.
Minimum value: 0
Maximum value: 4294967294

<b>priqDepth</b>
Queue depth threshold value per priorirty level. If the queue size (number of requests in the queue of that particular priorirty) on the virtual server to which this policy is bound, increases to the specified qDepth value, subsequent requests are dropped to the lowest priority level.
Minimum value: 0
Maximum value: 4294967294

<b>maxConn</b>
Maximum number of concurrent connections that can be open for requests that matches with rule.
Minimum value: 1
Maximum value: 4294967294

<b>delay</b>
Delay threshold, in microseconds, for requests that match the policy's rule. If the delay statistics gathered for the matching request exceed the specified delay, configured action triggered for that request, if there is no action then requests are dropped to the lowest priority level
Minimum value: 1
Maximum value: 599999999

<b>dosTrigExpression</b>
Optional expression to add second level check to trigger DoS actions. Specifically used for Analytics based DoS response generation

<b>dosAction</b>
DoS Action to take when vserver will be considered under DoS attack and corresponding rule matches. Mandatory if AppQoE actions are to be used for DoS attack prevention.
Possible values: SimpleResponse, HICResponse

<b>tcpprofile</b>
Bind TCP Profile based on L2/L3/L7 parameters.



##rm appqoe action

Removes the specified AppQoE action.


##Synopsys

rm appqoe action &lt;name>


##Arguments

<b>name</b>
Name of the action to be removed.



##set appqoe action

Set the argument of specified AppQoE action.


##Synopsys

set appqoe action &lt;name> [-priority &lt;priority>] [-altContentSvcName &lt;string>] [-altContentPath &lt;string>] [-polqDepth &lt;positive_integer>] [-priqDepth &lt;positive_integer>] [-maxConn &lt;positive_integer>] [-delay &lt;usecs>] [-dosTrigExpression &lt;expression>] [-dosAction ( SimpleResponse | HICResponse )] [-tcpprofile &lt;string>]


##Arguments

<b>name</b>
Name for the AppQoE action. Must begin with a letter, number, or the underscore symbol (_). Other characters allowed, after the first character, are the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), and colon (:) characters. This is a mandatory argument

<b>priority</b>
Priority for queuing the request. If server resources are not available for a request that matches the configured rule, this option specifies a priority for queuing the request until the server resources are available again. If priority is not configured then Lowest priority will be used to queue the request.
Possible values: HIGH, MEDIUM, LOW, LOWEST

<b>altContentSvcName</b>
Name of the alternative content service to be used in the ACS

<b>altContentPath</b>
Path to the alternative content service to be used in the ACS

<b>polqDepth</b>
Policy queue depth threshold value. When the policy queue size (number of requests queued for the policy binding this action is attached to) increases to the specified polqDepth value, subsequent requests are dropped to the lowest priority level.
Minimum value: 0
Maximum value: 4294967294

<b>priqDepth</b>
Queue depth threshold value per priorirty level. If the queue size (number of requests in the queue of that particular priorirty) on the virtual server to which this policy is bound, increases to the specified qDepth value, subsequent requests are dropped to the lowest priority level.
Minimum value: 0
Maximum value: 4294967294

<b>maxConn</b>
Maximum number of concurrent connections that can be open for requests that matches with rule.
Minimum value: 1
Maximum value: 4294967294

<b>delay</b>
Delay threshold, in microseconds, for requests that match the policy's rule. If the delay statistics gathered for the matching request exceed the specified delay, configured action triggered for that request, if there is no action then requests are dropped to the lowest priority level
Minimum value: 1
Maximum value: 599999999

<b>dosTrigExpression</b>
Optional expression to add second level check to trigger DoS actions. Specifically used for Analytics based DoS response generation

<b>dosAction</b>
DoS Action to take when vserver will be considered under DoS attack and corresponding rule matches. Mandatory if AppQoE actions are to be used for DoS attack prevention.
Possible values: SimpleResponse, HICResponse

<b>tcpprofile</b>
Bind TCP Profile based on L2/L3/L7 parameters.



##unset appqoe action

Use this command to remove appqoe action settings.Refer to the set appqoe action command for meanings of the arguments.


##Synopsys

unset appqoe action &lt;name> [-priority] [-altContentSvcName] [-altContentPath] [-polqDepth] [-priqDepth] [-maxConn] [-delay] [-dosAction] [-tcpprofile]


##show appqoe action

Display configured AppQoE action(s).


##Synopsys

show appqoe action [&lt;name>]


##Arguments

<b>name</b>
Name for the AppQoE action. Must begin with a letter, number, or the underscore symbol (_). Other characters allowed, after the first character, are the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), and colon (:) characters. This is a mandatory argument



##Outputs

<b>stateflag</b>

<b>hits</b>

<b>priority</b>
Priority for queuing the request. If server resources are not available for a request that matches the configured rule, this option specifies a priority for queuing the request until the server resources are available again. If priority is not configured then Lowest priority will be used to queue the request.

<b>respondWith</b>
Responder action to be taken when the threshold is reached. Available settings function as follows:
            ACS - Serve content from an alternative content service
                  Threshold : maxConn or delay
            NS - Serve from the NetScaler appliance (built-in response)
                 Threshold : maxConn or delay

<b>polqDepth</b>
Policy queue depth threshold value. When the policy queue size (number of requests queued for the policy binding this action is attached to) increases to the specified polqDepth value, subsequent requests are dropped to the lowest priority level.

<b>priqDepth</b>
Queue depth threshold value per priorirty level. If the queue size (number of requests in the queue of that particular priorirty) on the virtual server to which this policy is bound, increases to the specified qDepth value, subsequent requests are dropped to the lowest priority level.

<b>altContentSvcName</b>
Name of the alternative content service to be used in the ACS

<b>altContentPath</b>
Path to the alternative content service to be used in the ACS

<b>maxConn</b>
Maximum number of concurrent connections that can be open for requests that matches with rule.

<b>delay</b>
Delay threshold, in microseconds, for requests that match the policy's rule. If the delay statistics gathered for the matching request exceed the specified delay, configured action triggered for that request, if there is no action then requests are dropped to the lowest priority level

<b>CustomFile</b>
name of the HTML page object to use as the response

<b>dosTrigExpression</b>
Optional expression to add second level check to trigger DoS actions. Specifically used for Analytics based DoS response generation

<b>dosAction</b>
DoS Action to take when vserver will be considered under DoS attack and corresponding rule matches. Mandatory if AppQoE actions are to be used for DoS attack prevention.

<b>tcpprofile</b>
Bind TCP Profile based on L2/L3/L7 parameters.

<b>devno</b>

<b>count</b>



