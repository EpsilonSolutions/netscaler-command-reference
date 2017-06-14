#rewrite param

The following operations can be performed on "rewrite param":


[set](#set-rewrite-param) | [unset](#unset-rewrite-param) | [show](#show-rewrite-param)

##set rewrite param

Sets the default rewrite undefined action. If an UNDEF event is triggered during policy evaluation and if no undefAction is specified for the current policy, this value is used.


##Synopsys

set rewrite param -undefAction &lt;string>


##Arguments

<b>undefAction</b>
Action to perform if the result of policy evaluation is undefined (UNDEF). An UNDEF event indicates an internal error condition.
Available settings function as follows:
* NOOP - Send the request to the protected server instead of responding to it.
* RESET - Reset the request and notify the user?s browser, so that the user can resend the request.
* DROP - Drop the request without sending a response to the user.
Default value: "NOREWRITE"



##Example

set rewrite param -undefAction RESET

##unset rewrite param

Resets the global undefAction to NOREWRITE..Refer to the set rewrite param command for meanings of the arguments.


##Synopsys

unset rewrite param -undefAction


##Example

unset rewrite param -undefAction

##show rewrite param

Displays the default rewrite undefAction.


##Synopsys

show rewrite param


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>undefAction</b>
Name of the rewrite action.



##Example

show rewrite param

