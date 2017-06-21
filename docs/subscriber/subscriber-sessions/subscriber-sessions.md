#subscriber sessions

The following operations can be performed on "subscriber sessions":


[clear](#clear-subscriber-sessions) | [show](#show-subscriber-sessions)

##clear subscriber sessions

Deletes a subscriber session. Without any arguement it clears the subscriber session database.


##Synopsys

clear subscriber sessions [&lt;ip>@]


##Arguments

<b>ip</b>
Subscriber IP Address.



##Example

clear subscriber session or \\nclear subscriber session 3.3.3.3

##show subscriber sessions

show command of a subscriber session


##Synopsys

show subscriber sessions [&lt;ip>@]


##Arguments

<b>ip</b>
Subscriber IP Address.



##Outputs

<b>subscriptionIdType</b>
Subscription-Id type

<b>subscriptionIdvalue</b>
Subscription-Id value

<b>subscriberRules</b>
Rules stored in this session for this subscriber. When PCRF sends Charging-Rule-Name or Charging-Rule-Base-Name AVP for a subscriber, Netscaler stores these AVPs in the subscriber session. These Rules can be retreived using 'Subscriber.Rule_Active(&lt;rule name>)' expression. For static subscriber profiles, these rules are configured using '-subscriberRules &lt;list of rules>'.

<b>stateflag</b>
Flags controlling the display.

<b>flags</b>
Subscriber Session flags.

<b>TTL</b>
Subscriber Session Activity Timeout remaining. Netscaler will send a CCR-U after ttl expires. If subscriber sessions is a negative session, then Netscaler will send a CCR-I after TTL expires. Negative Sessions are sessions which have not been resolved by PCRF and instead of polling PCRF continously, Netscaler has installed a negative session. If default subscriber is configued, then Negative Sessions inherits default subscriber profile.

<b>avpdisplaybuffer</b>
Subscriber Attributes Display.

<b>servicePath</b>
Name of the servicepath to be taken for this subscriber.

<b>devno</b>

<b>count</b>



##Example

show subscriber session 10.102.217.4

