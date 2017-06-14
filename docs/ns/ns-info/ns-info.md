#ns info

The following operations can be performed on "ns info":


##show ns info

Displays the following details of the NetScaler appliance:* Software version* NetScaler IP address and subnet mask* Number of mapped IP addresses* Identifies the appliance as a standalone appliance, a part of an HA pair, or is a cluster node* Current time on the system and timestamp when the appliance was last updated* Features that are enabled or disabled* Modes that are enabled or disabled


##Synopsys

show ns info


##Example

An example of this command's output is shown below:System Rainier: Build 24, Date: Apr 25 2002, 21:13:25System IP: 10.101.4.22	(mask: 255.255.0.0)Mapped IP: 10.101.4.23Node: StandaloneHTTP port(s): (none)Max connections: 0Max requests per connection: 0Client IP insertion enabled: NOCookie version: 0Feature status:Web Logging: ONSurge Protection: ONLoad Balancing: ONContent Switching: ONCache Redirection: ONSure Connect: ONCompression Control: OFFPriority Queuing: ONSSL Offloading: ONGlobal Server Load Balancing: ONHTTP DoS Protection: OFFN+1: OFFDynamic Routing: OFFContent Filtering: ONInternal Caching: ONSSL VPN: OFFMode status:Fast Ramp: ONLayer 2 mode: ONUse Source IP: OFFClient Keep-alive: ONTCP Buffering: OFFMAC-based forwarding: ONEdge configuration: OFFUse Subnet IP: OFFLayer 3 mode (ip forwarding): ON

