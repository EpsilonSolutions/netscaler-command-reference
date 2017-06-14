#ns limitSessions

The following operations can be performed on "ns limitSessions":


[show](#show-ns-limitsessions) | [clear](#clear-ns-limitsessions)

##show ns limitSessions

Displays the rate limit sessions available on the appliance.


##Synopsys

show ns limitSessions &lt;limitIdentifier> [-detail]


##Arguments

<b>limitIdentifier</b>
Name of the rate limit identifier for which to display the sessions.

<b>detail</b>
Show the individual hash values.



##Outputs

<b>timeout</b>
The time remaining on the session before a flush can be attempted. If active transactions are present the session will not be flushed

<b>hits</b>
The number of times this entry was hit.

<b>drop</b>
The number of times action was taken.

<b>number</b>
The hash of the matched selectlets.

<b>name</b>
The string formed by gathering selectlet values.

<b>unit</b>
Total computed hash of the matched selectlets.

<b>flags</b>
Used internally to identify ip addresses.

<b>referenceCount</b>
Total number of transactions pointing to this entry. Its the sum total of the connection and bandwidth references

<b>maxBandwidth</b>
The current bandwidth

<b>SelectorIPV61</b>
First IPV6 address gathered.

<b>SelectorIPV62</b>
Second IPV6 address gathered.

<b>flag</b>
Used internally to identify ipv6 addresses.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##clear ns limitSessions

Clears the rate limit sessions available on the appliance.


##Synopsys

clear ns limitSessions &lt;limitIdentifier>


##Arguments

<b>limitIdentifier</b>
Name of the rate limit identifier for which the sessions must be cleared.



