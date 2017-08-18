#ns feature

The following operations can be performed on "ns feature":


[enable](#enable-ns-feature) | [disable](#disable-ns-feature) | [show](#show-ns-feature)

##enable ns feature

Enables NetScaler feature(s).


##Synopsys

enable ns feature &lt;feature> ...


##Arguments

<b>feature</b>
Feature to be enabled. Multiple features can be specified by providing a blank space between each feature.



##Example

enable ns feature scThis CLI command enables the SureConnect feature.

##disable ns feature

Disables NetScaler feature(s).


##Synopsys

disable ns feature &lt;feature> ...


##Arguments

<b>feature</b>
Feature to be disabled. Multiple features can be specified by providing a blank space between each feature.



##Related Commands

<ul><li><a href="../../../ns/ns">disable ns mode</a></li></ul>



##show ns feature

Displays the current state of NetScaler features.


##Synopsys

show ns feature


##Outputs

<b>feature</b>
Feature to be enabled. Multiple features can be specified by providing a blank space between each feature.

<b>WL</b>
Web Logging.

<b>SP</b>
Surge Protection.

<b>LB</b>
Load Balancing.

<b>CS</b>
Content Switching.

<b>CR</b>
Cache Redirect.

<b>SC</b>
Sure Connect.

<b>CMP</b>
Compression.

<b>PQ</b>
Priority Queuing.

<b>SSL</b>
Secure Sockets Layer.

<b>GSLB</b>
Global Server Load Balancing.

<b>HDOSP</b>
DOS Protection.

<b>Routing</b>
Routing.

<b>CF</b>
Content Filter.

<b>IC</b>
Integrated Caching.

<b>SSLVPN</b>
SSL VPN.

<b>AAA</b>
AAA

<b>OSPF</b>
OSPF Routing.

<b>RIP</b>
RIP Routing.

<b>BGP</b>
BGP Routing.

<b>REWRITE</b>
Rewrite.

<b>IPv6PT</b>
IPv6 protocol translation

<b>AppFw</b>
Application Firewall.

<b>RESPONDER</b>
Responder.

<b>HTMLInjection</b>
HTML Injection.

<b>push</b>
NetScaler Push.

<b>AppFlow</b>
AppFlow.

<b>CloudBridge</b>
CloudBridge.

<b>ISIS</b>
ISIS Routing.

<b>CH</b>
Call Home.

<b>AppQoE</b>
AppQoS

<b>DiskCaching</b>
Integrated Disk Cache

<b>ContentAccelerator</b>
Transparent Integrated Caching.

<b>RISE</b>
RISE

<b>FEO</b>
Optimize Web content (HTML, CSS, JavaScript, images)

<b>LSN</b>
Large Scale NAT.

<b>RDPProxy</b>
RDPPROXY.

<b>Rep</b>
Reputation Services.

<b>URLFiltering</b>
URL Filtering.

<b>VideoOptimization</b>
Video Optimization.



