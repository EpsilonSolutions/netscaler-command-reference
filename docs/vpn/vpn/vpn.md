#vpn

The following operations can be performed on "vpn":


##stat vpn

Displays the statistics for NetScaler Gateway usage. Displays event information, such as the event that generated the message, a time stamp, the message type, and predefined log levels and message information.


##Synopsys

stat vpn [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>Login-page requests received (iHtHit)</b>
Number of requests for VPN login page.

<b>Login-page delivery failures (iHtFail)</b>
Number of failures to display VPN login page.

<b>Client-configuration requests (cfgHit)</b>
Number of client configuration requests received by VPN server.

<b>DNS queries resolved (dnsHit)</b>
Number of DNS queries resolved by VPN server.

<b>WINS queries resolved (winsHit)</b>
Number of WINS queries resolved by VPN server.

<b>Number of SSLVPN tunnels (csHit)</b>
Number of SSL VPN tunnels formed between VPN server and client.

<b>Backend non-HTTP server probes (csNoHttp)</b>
Number of probes from VPN to back-end non-HTTP servers that have been accessed by the VPN client.

<b>Backend HTTP server probes (csHttp)</b>
Number of probes from VPN to back-end HTTP servers that have been accessed by the VPN client.

<b>Backend server probe successes (csConSuc)</b>
Number of successful probes to all back-end servers.

<b>File-system requests received (totFsHit)</b>
Number of file system requests received by VPN server.

<b>IIP disabled and MIP used (IIPdMIPu)</b>
Number of times MIP is used as IIP is disabled.

<b>IIP failed and MIP used (IIPfMIPu)</b>
Number of times MIP is used as IIP assignment failed.

<b>IIP spillover and MIP used (IIPsMIPu)</b>
Number of times MIP is used on IIP Spillover.

<b>IIP disabled and MIP disabled (IIPdMIPd)</b>
Both IIP and MIP is disabled.

<b>IIP failed and MIP disabled (IIPfMIPd)</b>
Number of times IIP assignment failed and MIP is disabled.

<b>SOCKS method request received (SOCKSmReqR)</b>
Number of received SOCKS method request.

<b>SOCKS method request sent (SOCKSmReqS)</b>
Number of sent SOCKS method request.

<b>SOCKS method response received (SOCKSmRespR)</b>
Number of received SOCKS method response.

<b>SOCKS method response sent (SOCKSmRespS)</b>
Number of sent SOCKS method response.

<b>SOCKS connect request received (SOCKScReqR)</b>
Number of received SOCKS connect request.

<b>SOCKS connect request sent (SOCKScReqS)</b>
Number of sent SOCKS connect request.

<b>SOCKS connect response received (SOCKScRespR)</b>
Number of received SOCKS connect response.

<b>SOCKS connect response sent (SOCKScRespS)</b>
Number of sent SOCKS connect response.

<b>SOCKS server error (SOCKSserverErr)</b>
Number of SOCKS server error.

<b>SOCKS client error (SOCKSclientErr)</b>
Number of SOCKS client error.

<b>STA connection success (STAconnSucc)</b>
Number of STA connection success.

<b>STA connection failure (STAconnFail)</b>
Number of STA connection failure.

<b>CPS connection success (CPSconnSucc)</b>
Number of CPS connection success.

<b>CPS connection failure (CPSconnFail)</b>
Number of CPS connection failure.

<b>STA request sent (STAreqSent)</b>
Number of STA request sent.

<b>STA response received (STArespRecvd)</b>
Number of STA response received.

<b>ICA license failure (ICAlicenseFail)</b>
Number of ICA license failure.



##Related Commands

<ul><li><a href="../../../t-vpn-vs/t-vpn-vs">stat vpn vserver</a></li></ul>



