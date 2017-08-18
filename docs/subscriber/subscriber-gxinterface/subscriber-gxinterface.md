#subscriber gxInterface

The following operations can be performed on "subscriber gxInterface":


[set](#set-subscriber-gxinterface) | [unset](#unset-subscriber-gxinterface) | [show](#show-subscriber-gxinterface)

##set subscriber gxInterface

Set the Gx Interface configuration on NS.


##Synopsys

set subscriber gxInterface [-vServer &lt;string>] [-service &lt;string>] [-pcrfRealm &lt;string>] [-holdOnSubscriberAbsence ( YES | NO )] [-requestTimeout &lt;positive_integer>] [-requestRetryAttempts &lt;positive_integer>] [-revalidationTimeout &lt;positive_integer>] [-negativeTTL &lt;positive_integer>] [-servicePathAVP &lt;positive_integer> ...] [-servicePathVendorid &lt;positive_integer>]


##Arguments

<b>vServer</b>
Name of the load balancing, or content switching vserver to which the Gx connections are established. The service type of the virtual server must be DIAMETER/SSL_DIAMETER. Mutually exclusive with the service parameter. Therefore, you cannot set both service and the Virtual Server in the Gx Interface.

<b>service</b>
Name of DIAMETER/SSL_DIAMETER service corresponding to PCRF to which the Gx connection is established. The service type of the service must be DIAMETER/SSL_DIAMETER. Mutually exclusive with vserver parameter. Therefore, you cannot set both Service and the Virtual Server in the Gx Interface.

<b>pcrfRealm</b>
PCRF realm is of type DiameterIdentity and contains the realm of PCRF to which the message is to be routed. This is the realm used in Destination-Realm AVP by Netscaler Gx client (as a Diameter node).

<b>holdOnSubscriberAbsence</b>
Set this setting to yes if Netscaler needs to Hold pakcets till subscriber session is fetched from PCRF. Else set to NO. By default set to yes. If this setting is set to NO, then till NetScaler fetches subscriber from PCRF, default subscriber profile will be applied to this subscriber if configured. If default subscriber profile is also not configured an undef would be raised to expressions which use Subscriber attributes. 
Possible values: YES, NO
Default value: NO

<b>requestTimeout</b>
q!Time, in seconds, within which the Gx CCR request must complete. If the request does not complete within this time, the request is retransmitted for requestRetryAttempts time. If still reuqest is not complete then default subscriber profile will be applied to this subscriber if configured. If default subscriber profile is also not configured an undef would be raised to expressions which use Subscriber attributes.
Zero disables the timeout. !
Default value: 10
Minimum value: 0
Maximum value: 86400

<b>requestRetryAttempts</b>
If the request does not complete within requestTimeout time, the request is retransmitted for requestRetryAttempts time.
Default value: 3
Minimum value: 0

<b>revalidationTimeout</b>
q!Revalidation Timeout, in seconds, after which the Gx CCR-U request will be sent after any PCRF activity on a session. Any RAR or CCA message resets the timer.
Zero value disables the idle timeout. !
Default value: 0
Minimum value: 0
Maximum value: 86400

<b>negativeTTL</b>
q!Negative TTL, in seconds, after which the Gx CCR-I request will be resent for sessions that have not been resolved by PCRF due to server being down or no response or failed response. Instead of polling the PCRF server constantly, negative-TTL makes NS stick to un-resolved session. Meanwhile Netscaler installs a negative session to avoid going to PCRF.
For Negative Sessions, Netcaler inherits the attributes from default subscriber profile if default subscriber is configured. A default subscriber could be configured as 'add subscriber profile *'. Or these attributes can be inherited from Radius as well if Radius is configued.
Zero value disables the Negative Sessions. And Netscaler does not install Negative sessions even if subscriber session could not be fetched. !
Default value: 600
Minimum value: 0
Maximum value: 86400

<b>servicePathAVP</b>
The AVP code in which PCRF sends service path applicable for subscriber.
Minimum value: 1

<b>servicePathVendorid</b>
The vendorid of the AVP in which PCRF sends service path for subscriber.
Minimum value: 0



##unset subscriber gxInterface

Use this command to remove subscriber gxInterface settings.Refer to the set subscriber gxInterface command for meanings of the arguments.


##Synopsys

unset subscriber gxInterface [-vServer] [-service] [-holdOnSubscriberAbsence] [-requestTimeout] [-requestRetryAttempts] [-revalidationTimeout] [-negativeTTL] [-servicePathAVP] [-servicePathVendorid]


##show subscriber gxInterface

Displays the Gx interface parameters configured on the NetScaler appliance.


##Synopsys

show subscriber gxInterface


##Outputs

<b>vServer</b>
Name of the load balancing, or content switching vserver to which the Gx connections are established. The service type of the virtual server must be DIAMETER/SSL_DIAMETER. Mutually exclusive with the service parameter. Therefore, you cannot set both service and the Virtual Server in the Gx Interface.

<b>service</b>
Name of DIAMETER/SSL_DIAMETER service corresponding to PCRF to which the Gx connection is established. The service type of the service must be DIAMETER/SSL_DIAMETER. Mutually exclusive with vserver parameter. Therefore, you cannot set both Service and the Virtual Server in the Gx Interface.

<b>svrState</b>
The state of the gx service.

<b>pcrfRealm</b>
PCRF realm is of type DiameterIdentity and contains the realm of PCRF to which the message is to be routed. This is the realm used in Destination-Realm AVP by Netscaler Gx client (as a Diameter node).

<b>holdOnSubscriberAbsence</b>
Set this setting to yes if Netscaler needs to Hold pakcets till subscriber session is fetched from PCRF. Else set to NO. By default set to yes. If this setting is set to NO, then till NetScaler fetches subscriber from PCRF, default subscriber profile will be applied to this subscriber if configured. If default subscriber profile is also not configured an undef would be raised to expressions which use Subscriber attributes.

<b>requestTimeout</b>
q!Time, in seconds, within which the Gx CCR request must complete. If the request does not complete within this time, the request is retransmitted for requestRetryAttempts time. If still reuqest is not complete then default subscriber profile will be applied to this subscriber if configured. If default subscriber profile is also not configured an undef would be raised to expressions which use Subscriber attributes.
Zero disables the timeout. !

<b>requestRetryAttempts</b>
If the request does not complete within requestTimeout time, the request is retransmitted for requestRetryAttempts time.

<b>idleTTL</b>
q!Idle Time, in seconds, after which the Gx CCR-U request will be sent after any PCRF activity on a session. Any RAR or CCA message resets the timer.
Zero value disables the idle timeout. !

<b>revalidationTimeout</b>
q!Revalidation Timeout, in seconds, after which the Gx CCR-U request will be sent after any PCRF activity on a session. Any RAR or CCA message resets the timer.
Zero value disables the idle timeout. !

<b>negativeTTL</b>
q!Negative TTL, in seconds, after which the Gx CCR-I request will be resent for sessions that have not been resolved by PCRF due to server being down or no response or failed response. Instead of polling the PCRF server constantly, negative-TTL makes NS stick to un-resolved session. Meanwhile Netscaler installs a negative session to avoid going to PCRF.
For Negative Sessions, Netcaler inherits the attributes from default subscriber profile if default subscriber is configured. A default subscriber could be configured as 'add subscriber profile *'. Or these attributes can be inherited from Radius as well if Radius is configued.
Zero value disables the Negative Sessions. And Netscaler does not install Negative sessions even if subscriber session could not be fetched. !

<b>identity</b>
DiameterIdentity to be used by NS. DiameterIdentity is used to identify a Diameter node uniquely. Before setting up diameter configuration, Netscaler (as a Diameter node) MUST be assigned a unique DiameterIdentity.
example =>
set ns diameter -identity netscaler.com
Now whenever Netscaler system needs to use identity in diameter messages. It will use 'netscaler.com' as Origin-Host AVP as defined in RFC3588

<b>realm</b>
Diameter Realm to be used by NS.
example =>
set ns diameter -realm com
Now whenever Netscaler system needs to use realm in diameter messages. It will use 'com' as Origin-Realm AVP as defined in RFC3588

<b>status</b>
NetScaler PCRF connection Status. (Gx Protocol State)

<b>servicePathAVP</b>
The AVP code in which PCRF sends service path applicable for subscriber.

<b>servicePathVendorid</b>
The vendorid of the AVP in which PCRF sends service path for subscriber.

<b>servicePathInfomode</b>
The type of info in which service path is passed from PCRF,
            SERVICE_FUNCTION: Denotes the service chain is passed as servicefunction names in-order in AVPS with code servicepathAVP
            SERVICE_PATH: Denotes the service path name is passed in AVPS with code servicepathAVP.q



