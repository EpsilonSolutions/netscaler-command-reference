#subscriber param

The following operations can be performed on "subscriber param":


[set](#set-subscriber-param) | [unset](#unset-subscriber-param) | [show](#show-subscriber-param)

##set subscriber param

Modifies the subscriber params.


##Synopsys

set subscriber param [-keytype IP] [-interfaceType &lt;interfaceType>] [-idleTTL &lt;positive_integer>] [-idleAction &lt;idleAction>] [-ipv6PrefixLookupList &lt;positive_integer> ...]


##Arguments

<b>keytype</b>
Type of subscriber key type IP or IPANDVLAN
Possible values: IP
Default value: IP

<b>interfaceType</b>
Subscriber Interface refers to Netscaler interaction with control plane protocols, RADIUS and GX.
Types of subscriber interface: NONE, RadiusOnly, RadiusAndGx, GxOnly.
NONE: Only static subscribers can be configured.
RadiusOnly: GX interface is absent. Subscriber information is obtained through RADIUS Accounting messages.
RadiusAndGx: Subscriber ID obtained through RADIUS Accounting is used to query PCRF. Subscriber information is obtained from both RADIUS and PCRF.
GxOnly: RADIUS interface is absent. Subscriber information is queried using Subscriber IP.
Possible values: None, RadiusOnly, RadiusAndGx, GxOnly
Default value: None

<b>idleTTL</b>
q!Idle Timeout, in seconds, after which Netscaler will take an idleAction on a subscriber session (refer to 'idleAction' arguement in 'set subscriber param' for more details on idleAction). Any data-plane or control plane activity updates the idleTimeout on subscriber session. idleAction could be to 'just delete the session' or 'delete and CCR-T' (if PCRF is configured) or 'do not delete but send a CCR-U'. 
Zero value disables the idle timeout. !
Default value: 0
Minimum value: 0
Maximum value: 172800

<b>idleAction</b>
q!Once idleTTL exprires on a subscriber session, Netscaler will take an idle action on that session. idleAction could be chosen from one of these ==&gt;
1. ccrTerminate: (default) send CCR-T to inform PCRF about session termination and delete the session.  
2. delete: Just delete the subscriber session without informing PCRF.
3. ccrUpdate: Do not delete the session and instead send a CCR-U to PCRF requesting for an updated session. !
Possible values: ccrTerminate, delete, ccrUpdate
Default value: ccrTerminate

<b>ipv6PrefixLookupList</b>
The ipv6PrefixLookupList should consist of all the ipv6 prefix lengths assigned to the UE's'
Minimum value: 1
Maximum value: 128



##unset subscriber param

Use this command to remove subscriber param settings.Refer to the set subscriber param command for meanings of the arguments.


##Synopsys

unset subscriber param [-keytype] [-interfaceType] [-idleTTL] [-idleAction]


##show subscriber param

displays global subscriber params.


##Synopsys

show subscriber param


##Outputs

<b>keytype</b>
Type of subscriber key type IP or IPANDVLAN

<b>interfaceType</b>
Subscriber Interface refers to Netscaler interaction with control plane protocols, RADIUS and GX.
Types of subscriber interface: NONE, RadiusOnly, RadiusAndGx, GxOnly.
NONE: Only static subscribers can be configured.
RadiusOnly: GX interface is absent. Subscriber information is obtained through RADIUS Accounting messages.
RadiusAndGx: Subscriber ID obtained through RADIUS Accounting is used to query PCRF. Subscriber information is obtained from both RADIUS and PCRF.
GxOnly: RADIUS interface is absent. Subscriber information is queried using Subscriber IP.

<b>idleTTL</b>
q!Idle Timeout, in seconds, after which Netscaler will take an idleAction on a subscriber session (refer to 'idleAction' arguement in 'set subscriber param' for more details on idleAction). Any data-plane or control plane activity updates the idleTimeout on subscriber session. idleAction could be to 'just delete the session' or 'delete and CCR-T' (if PCRF is configured) or 'do not delete but send a CCR-U'. 
Zero value disables the idle timeout. !

<b>idleAction</b>
q!Once idleTTL exprires on a subscriber session, Netscaler will take an idle action on that session. idleAction could be chosen from one of these ==>
1. ccrTerminate: (default) send CCR-T to inform PCRF about session termination and delete the session.  
2. delete: Just delete the subscriber session without informing PCRF.
3. ccrUpdate: Do not delete the session and instead send a CCR-U to PCRF requesting for an updated session. !

<b>ipv6PrefixLookupList</b>
The ipv6PrefixLookupList should consist of all the ipv6 prefix lengths assigned to the UE's'

<b>builtin</b>



