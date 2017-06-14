#aaa session

The following operations can be performed on "aaa session":


[show](#show-aaa-session) | [kill](#kill-aaa-session)

##show aaa session

Displays all AAA-TM/VPN connections that are bound to the specified user, group, IP address, or IP range.


##Synopsys

show aaa session [-userName &lt;string>] [-groupName &lt;string>] [-intranetIP &lt;ip_addr|*> [&lt;netmask>]]


##Arguments

<b>userName</b>
Name of the AAA user.

<b>groupName</b>
Name of the AAA group.

<b>intranetIP</b>
IP address or the first address in the intranet IP range.



##Outputs

<b>publicIP</b>
Client's public IP address

<b>publicPort</b>
Client's public port

<b>IPAddress</b>
NetScaler's IP address

<b>port</b>
NetScaler's port

<b>privateIP</b>
Client's private/mapped IP address

<b>privatePort</b>
Client's private/mapped port

<b>destIP</b>
Destination IP address

<b>destPort</b>
Destination port

<b>intranetIP</b>
Specifies the Intranet IP

<b>peId</b>
Core id of the session owner

<b>stateflag</b>

<b>devno</b>

<b>count</b>



##Example

&gt; show aaa connection ClintIp (ClientPort) -&gt; ServerIp(ServerPort) ------------------------- ---------------------------- User Name: Joe 10.102.0.39 (2318 ) -&gt; 10.102.4.245 (443 ) 10.102.0.39 (2320 ) -&gt; 10.102.4.245 (443 ) 10.102.0.39 (2340 ) -&gt; 10.102.4.245 (443 ) Done &gt;

##kill aaa session

Terminates the specified AAA-TM/VPN session.


##Synopsys

kill aaa session [-userName &lt;string>] [-groupName &lt;string>] [-intranetIP &lt;ip_addr|*> [&lt;netmask>]] [-all]


##Arguments

<b>userName</b>
Terminate AAA-TM/VPN sessions that belong to the specified user.

<b>groupName</b>
Terminate AAA-TM/VPN sessions that belong to any user that is a member of the specified group.

<b>intranetIP</b>
Terminate AAA-TM/VPN sessions that are associated with the specified intranet IP address or with an address in the range specified by the address and subnet mask.

<b>all</b>
Terminate all active AAA-TM/VPN sessions.



##Example

kill aaa session -user joe

