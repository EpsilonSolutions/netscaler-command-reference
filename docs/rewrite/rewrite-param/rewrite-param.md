#rewrite param

The following operations can be performed on "rewrite param":


[set](#set-rewrite-param) | [unset](#unset-rewrite-param) | [show](#show-rewrite-param)

##set rewrite param

Sets the given Rewrite parameter(s).


##Synopsys

set rewrite param [-undefAction &lt;string>] [-timeout &lt;positive_integer>]


##Arguments

<b>undefAction</b>
Action to perform if the result of policy evaluation is undefined (UNDEF). An UNDEF event indicates an error condition in evaluating the expression.
Available settings function as follows:
* NOREWRITE - Do not modify the message.
* RESET - Reset the connection and notify the user's browser, so that the user can resend the request.
* DROP - Drop the message without sending a response to the user.
Default value: "NOREWRITE"

<b>timeout</b>
Maximum time in milliseconds to allow for processing all the policies and their selected actions without interruption. If the timeout is reached then the evaluation causes an UNDEF to be raised and no further processing is performed. Note that some rewrites may have already been performed.
Minimum value: 1
Maximum value: 5000



##Example

set rewrite param -undefAction RESET

##unset rewrite param

Resets the given Rewrite parameter(s)..Refer to the set rewrite param command for meanings of the arguments.


##Synopsys

unset rewrite param [-undefAction] [-timeout]


##Example

unset rewrite param -undefAction

##show rewrite param

Displays the Rewrite parameters.


##Synopsys

show rewrite param


##Outputs

<b>undefAction</b>
Name of the rewrite action.

<b>timeout</b>
Execution timeout.



##Example

show rewrite param

