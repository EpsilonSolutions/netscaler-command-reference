#lldp neighbors

The following operations can be performed on "lldp neighbors":


[show](#show-lldp-neighbors) | [clear](#clear-lldp-neighbors)

##show lldp neighbors

Display Neighbor information per interface


##Synopsys

show lldp neighbors [&lt;ifnum>]


##Arguments

<b>ifnum</b>
Interface Name

<b>summary</b>

<b>fullValues</b>



##Outputs

<b>chassisIdSubtype</b>
Chassis id sub type

<b>chassisId</b>
Chassis Id

<b>portIdSubtype</b>
Port id subtype

<b>portId</b>
Port Id

<b>TTL</b>
Time to Live

<b>portDescription</b>
Port Description

<b>sys</b>
System Name

<b>sysDesc</b>
System Description

<b>mgmtAddressSubtype</b>
Management Address Type

<b>mgmtAddress</b>
Management Address

<b>iftype</b>
Interface subtype

<b>ifNumber</b>
Interface Number

<b>vlan</b>
vlan name

<b>vlanId</b>
Vlan Id

<b>portProtoSupported</b>
Flag to show Port Protocol Support

<b>portProtoEnabled</b>
Flag to show Port Protocol support enabled

<b>portProtoId</b>
Port Protocol ID

<b>portVlanId</b>
Port Vlan Id

<b>protocolId</b>
port vlan id name

<b>linkAggrCapable</b>
Is neighbor Link Aggregation Capable

<b>LinkAggrEnabled</b>
Is link aggregation Enabled

<b>linkAggrId</b>
Link Aggregation Id

<b>flag</b>

<b>sysCapabilities</b>
Acronyms for remote system capabilities:
OT : Other.
RE : Repeater(IETF RFC 2108).
BR : MAC Bridge(IEEE Std 802.1D).
WL : WLAN Access Point(IEEE Std 802.11 MIB).
RO : ROuter(IETF RFC 1812).
TE : Telephone(IETF RFC 4293).
DO : DOCSIS cable device(IETF RFC 4639 and IETF RFC 4546).
ST : STation only(IETF RFC 4293).
CV : C-VLAN component of a VLAN Bridge(IEEE Std 802.1Q).
SV : S-VLAN component of a VLAN Bridge(IEEE Std 802.1Q).
MR : Two port MAC Relay(IEEE Std 802.1Q).

<b>sysCapEnabled</b>
Acronyms for remote system enabled capabilities:
OT : Other.
RE : Repeater(IETF RFC 2108).
BR : MAC Bridge(IEEE Std 802.1D).
WL : WLAN Access Point(IEEE Std 802.11 MIB).
RO : ROuter(IETF RFC 1812).
TE : Telephone(IETF RFC 4293).
DO : DOCSIS cable device(IETF RFC 4639 and IETF RFC 4546).
ST : STation only(IETF RFC 4293).
CV : C-VLAN component of a VLAN Bridge(IEEE Std 802.1Q).
SV : S-VLAN component of a VLAN Bridge(IEEE Std 802.1Q).
MR : Two port MAC Relay(IEEE Std 802.1Q).

<b>autonegSupport</b>
MAC/PHY autonegotiation support

<b>autonegEnabled</b>
MAC/PHY autonegotiation enabled

<b>autonegAdvertised</b>
MAC/PHY autonegotiation advetised

<b>autonegMAUType</b>
MAC/PHY Medium Attachment Unit (MAU) type of the port. Description listed below:
AUI           - no internal MAU, view from AUI
10Base5       - thick coax MAU
Foirl         - FOIRL MAU
10Base2       - thin coax MAU
10BaseT       - UTP MAU
10BaseFP      - passive fiber MAU
10BaseFB      - sync fiber MAU
10BaseFL      - async fiber MAU
10Broad36     - broadband DTE MAU
10BaseTHD     - UTP MAU, half duplex mode
10BaseTFD     - UTP MAU, full duplex mode
10BaseFLHD    - async fiber MAU, half duplex mode
10BaseFLDF    - async fiber MAU, full duplex mode
10BaseT4      - 4 pair category 3 UTP
100BaseTXHD   - 2 pair category 5 UTP, half duplex mode
100BaseTXFD   - 2 pair category 5 UTP, full duplex mode
100BaseFXHD   - X fiber over PMT, half duplex mode
100BaseFXFD   - X fiber over PMT, full duplex mode
100BaseT2HD   - 2 pair category 3 UTP, half duplex mode
100BaseT2DF   - 2 pair category 3 UTP, full duplex mode
1000BaseXHD   - PCS/PMA, unknown PMD, half duplex mode
1000BaseXFD   - PCS/PMA, unknown PMD, full duplex mode
1000BaseLXHD  - Fiber over long-wavelength laser, half duplex mode
1000BaseLXFD  - Fiber over long-wavelength laser, full duplex mode
1000BaseSXHD  - Fiber over short-wavelength laser, half duplex mode
1000BaseSXFD  - Fiber over short-wavelength laser, full duplex mode
1000BaseCXHD  - Copper over 150-Ohm balanced cable, half duplex mode
1000BaseCXFD  - Copper over 150-Ohm balanced cable, full duplex mode
1000BaseTHD   - Four-pair Category 5 UTP, half duplex mode
1000BaseTFD   - Four-pair Category 5 UTP, full duplex mode
10GigBaseX    - X PCS/PMA, unknown PMD
10GigBaseLX4  - X fiber over WWDM optics
10GigBaseR    - R PCS/PMA, unknown PMD
10GigBaseER   - R fiber over 1550 nm optics
10GigBaseLR   - R fiber over 1310 nm optics
10GigBaseSR   - R fiber over 850 nm optics
10GigBaseW    - W PCS/PMA, unknown PMD
10GigBaseEW   - W fiber over 1550 nm optics
10GigBaseLW   - W fiber over 1310 nm optics
10GigBaseSW   - W fiber over 850 nm optics

<b>mtu</b>
MTU of Remote Device

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##clear lldp neighbors

Removes LLDP neighbor info of interfaces


##Synopsys

clear lldp neighbors


