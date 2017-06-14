#gslb ldnsentries

The following operations can be performed on "gslb ldnsentries":


[clear](#clear-gslb-ldnsentries) | [show](#show-gslb-ldnsentries)

##clear gslb ldnsentries

Clears all the local DNS (LDNS) entries created on the NetScaler appliance. LDNS entries store network metrics for RTT learned from the packets exchanged with LDNS servers.


##Synopsys

clear gslb ldnsentries


##show gslb ldnsentries

Displays the local DNS (LDNS) entries created on the NetScaler appliance. LDNS entries store network metrics for RTT learned from the packets exchanged with LDNS servers.


##Synopsys

show gslb ldnsentries


##Arguments

<b>summary</b>

<b>fullValues</b>



##Outputs

<b>siteName</b>
The GSLB site name

<b>numsites</b>
Specifies the number of gslb sites

<b>IPAddress</b>
IP address of the LDNS server

<b>TTL</b>
TTL value of the LDNS entry

<b>name</b>
Monitor that is currently being used to monitor the LDNS ip..

<b>rtt</b>
RTT value of the LDNS entry for all gslb sites

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show gslb ldnsentries

