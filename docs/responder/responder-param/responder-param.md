#responder param

The following operations can be performed on "responder param":


[set](#set-responder-param) | [unset](#unset-responder-param) | [show](#show-responder-param)

##set responder param

Sets the default responder undefined action. If an UNDEF event is triggered during policy evaluation and if no undefAction is specified for the current policy, this value is used.


##Synopsys

set responder param -undefAction &lt;string>


##Arguments

<b>undefAction</b>
Action to perform when policy evaluation creates an UNDEF condition. Available settings function as follows:
* NOOP - Send the request to the protected server.
* RESET - Reset the request and notify the user's browser, so that the user can resend the request.
* DROP - Drop the request without sending a response to the user.
Default value: "NOOP"



##Example

set responder param -undefAction RESET

##unset responder param

Resets the global undefAction to NOOP..Refer to the set responder param command for meanings of the arguments.


##Synopsys

unset responder param -undefAction


##Example

unset responder param -undefAction

##show responder param

Displays the default responder undefAction.


##Synopsys

show responder param


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>undefAction</b>
Name of the responder action.



##Example

show responder param

