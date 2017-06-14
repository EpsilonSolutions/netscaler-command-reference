#ns mode

The following operations can be performed on "ns mode":


[enable](#enable-ns-mode) | [disable](#disable-ns-mode) | [show](#show-ns-mode)

##enable ns mode

Enables NetScaler mode(s).


##Synopsys

enable ns mode &lt;Mode> ...


##Arguments

<b>Mode</b>
Mode to be enabled. Multiple modes can be specified by providing a blank space between each mode.



##Example

This CLI command enables the system's client keep-alive feature:enable ns mode CKA

##disable ns mode

Disables NetScaler mode(s).


##Synopsys

disable ns mode &lt;Mode> ...


##Arguments

<b>Mode</b>
Mode to be disabled. Multiple modes can be specified by providing a blank space between each mode.



##Example

This example shows the command to disable the system's client keep-alive feature:disable ns mode CKA

##show ns mode

Displays the current state of NetScaler modes.


##Synopsys

show ns mode


##Outputs

<b>Mode</b>
Mode to be enabled. Multiple modes can be specified by providing a blank space between each mode.

<b>FR</b>
Fast Ramp.

<b>L2</b>
Layer 2 mode.

<b>USIP</b>
Use Source IP.

<b>CKA</b>
Client Keep-alive.

<b>TCPB</b>
TCP Buffering.

<b>MBF</b>
MAC-based forwarding.

<b>Edge</b>
Edge configuration.

<b>USNIP</b>
Use Subnet IP.

<b>L3</b>
Layer 3 mode (ip forwarding).

<b>PMTUD</b>
Path MTU Discovery.

<b>SRADV</b>
Static Route Advertisement.

<b>DRADV</b>
Direct Route Advertisement.

<b>IRADV</b>
Intranet Route Advertisement.

<b>SRADV6</b>
Ipv6 Static Route Advertisement.

<b>DRADV6</b>
Ipv6 Direct Route Advertisement.

<b>BridgeBPDUs</b>
BPDU Bridging Mode.

<b>RISE_APBR</b>
APBR Publishing Mode.

<b>RISE_RHI</b>
RHI Publishing Mode.



