#subscriber profile

The following operations can be performed on "subscriber profile":


[add](#add-subscriber-profile) | [set](#set-subscriber-profile) | [unset](#unset-subscriber-profile) | [rm](#rm-subscriber-profile) | [show](#show-subscriber-profile)

##add subscriber profile

Creates a static subscriber profile for mobile subscribers. When traffic passes through Netscaler, Netscaler can identify the subscribers for this traffic and Subscriber based policy expressions could be configured to enable subscriber aware traffic processing.


##Synopsys

add subscriber profile &lt;ip>@ [-subscriberRules &lt;string> ...] [-subscriptionIdType &lt;subscriptionIdType>  -subscriptionIdvalue &lt;string>] [-servicePath &lt;string>]


##Arguments

<b>ip</b>
Subscriber ip address

<b>subscriberRules</b>
Rules configured for this subscriber. This is similar to rules received from PCRF for dynamic subscriber sessions.

<b>subscriptionIdType</b>
Subscription-Id type
Possible values: E164, IMSI, SIP_URI, NAI, PRIVATE

<b>subscriptionIdvalue</b>
Subscription-Id value

<b>servicePath</b>
Name of the servicepath to be taken for this subscriber.



##Example

add subscriber profile 10.102.217.4 -subscriberRules rule1 rule2

##set subscriber profile

Modifies a static subscriber


##Synopsys

set subscriber profile &lt;ip>@ [-subscriberRules &lt;string> ...] [-subscriptionIdType &lt;subscriptionIdType>] [-subscriptionIdvalue &lt;string>] [-servicePath &lt;string>]


##Arguments

<b>ip</b>
Subscriber ip address

<b>subscriberRules</b>
Rules configured for this subscriber. This is similar to rules received from PCRF for dynamic subscriber sessions.

<b>subscriptionIdType</b>
Subscription-Id type
Possible values: E164, IMSI, SIP_URI, NAI, PRIVATE

<b>subscriptionIdvalue</b>
Subscription-Id value

<b>servicePath</b>
Name of the servicepath to be taken for this subscriber.



##Example

set subscriber profile 10.102.217.4 -subscriberRules rule1 rule2

##unset subscriber profile

Use this command to remove subscriber profile settings.Refer to the set subscriber profile command for meanings of the arguments.


##Synopsys

unset subscriber profile &lt;ip>@ -servicePath


##rm subscriber profile

Deletes a static subscriber


##Synopsys

rm subscriber profile &lt;ip>@


##Arguments

<b>ip</b>
Subscriber ip address



##Example

rm subscriber profile 10.102.217.4

##show subscriber profile

show command of a static subscriber


##Synopsys

show subscriber profile [&lt;ip>@]


##Arguments

<b>ip</b>
Subscriber ip address



##Outputs

<b>subscriptionIdType</b>
Subscription-Id type

<b>subscriptionIdvalue</b>
Subscription-Id value

<b>subscriberRules</b>
Rules configured for this subscriber. This is similar to rules received from PCRF for dynamic subscriber sessions.

<b>stateflag</b>
Flags controlling the display.

<b>flags</b>
Subscriber Session flags

<b>TTL</b>
Subscriber Session TTL

<b>avpdisplaybuffer</b>
Subscriber Attributes Display

<b>servicePath</b>
Name of the servicepath to be taken for this subscriber.

<b>devno</b>

<b>count</b>



##Example

show subscriber profile 10.102.217.4

