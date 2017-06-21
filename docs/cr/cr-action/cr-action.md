#cr action

The following operations can be performed on "cr action":


##show cr action

Displays information about all the built-in or user defined cache redirection actions.


##Synopsys

show cr action [&lt;name>]


##Arguments

<b>name</b>
Name of the action for which to display detailed information.



##Outputs

<b>crType</b>
Type to decide where to redirect the requests if the cache redirection policy is hit.
The valid options are as follows:
*CACHE - Directs all the requests to the cache if cache redirection policy is hit.
*ORIGIN - Directs all requests to the origin server if the cache redirection policy is hit.

<b>stateflag</b>

<b>builtin</b>
Flag to determine whether CRACTION is default or not.

<b>isDefault</b>
A value of true is returned if it is a default cr action.

<b>hits</b>
The number of times the action has been taken.

<b>referenceCount</b>
The number of references to the action.

<b>undefHits</b>
The number of times the action resulted in UNDEF.

<b>comment</b>
Comment. Any type of information about this responder action.

<b>devno</b>

<b>count</b>



