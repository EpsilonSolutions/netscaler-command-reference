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
Subscriber Session revalidation Timeout remaining. This TTL gets refreshed when a radius or CCA or RAR message is received for this subscriber session.
Netscaler will send a CCR-U after revalidation timer expires.
If subscriber sessions is a negative session, then Netscaler will send a CCR-I after TTL expires. Negative Sessions are sessions which have not been resolved by PCRF and instead of polling PCRF continously, Netscaler has installed a negative session. If default subscriber is configued, then Negative Sessions inherits default subscriber profile.

<b>idleTTL</b>
Subscriber Session Activity Timeout remaining. Netscaler will take an idleAction after ttl expires. idleaction could be -->
1. ccrTerminate: (default) send CCR-T to inform PCRF about session termination and delete the session.  
2. delete: Just delete the subscriber session without informing PCRF.
3. ccrUpdate: Do not delete the session and instead send a CCR-U to PCRF requesting for an updated session.
      But if this is a negative session and idleaction is ccrUpdate then NS won't take any action. Also on negative sessions ccrTerminate translates to delete.

<b>avpdisplaybuffer</b>
Subscriber Attributes Display.

<b>servicePath</b>
Name of the servicepath to be taken for this subscriber.

<b>devno</b>

<b>count</b>



##Example

show subscriber session 10.102.217.4

