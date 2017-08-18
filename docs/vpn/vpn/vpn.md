#vpn

The following operations can be performed on "vpn":


##stat vpn

Displays the statistics for NetScaler Gateway usage. Displays event information, such as the event that generated the message, a time stamp, the message type, and predefined log levels and message information.


##Synopsys

stat vpn [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>detail</b>
Specifies detailed output (including more statistics). The output can be quite voluminous. Without this argument, the output will show only a summary.

<b>fullValues</b>
Specifies that numbers and strings should be displayed in their full form. Without this option, long strings are shortened and large numbers are abbreviated

<b>ntimes</b>
The number of times, in intervals of seven seconds, the statistics should be displayed.
Default value: 1
Minimum value: 0

<b>logFile</b>
The name of the log file to be used as input.

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

<b>VPN User License Not Available (licFail)</b>
Number of users not able to login because of license unavailability.

<b>IIP disabled and SNIP used (IIPdMIPu)</b>
Number of times SNIP is used as IIP is disabled.

<b>IIP failed and SNIP used (IIPfMIPu)</b>
Number of times SNIP is used as IIP assignment failed.

<b>IIP spillover and SNIP used (IIPsMIPu)</b>
Number of times SNIP is used on IIP Spillover.

<b>IIP disabled and SNIP disabled (IIPdMIPd)</b>
Both IIP and SNIP is disabled.

<b>IIP failed and SNIP disabled (IIPfMIPd)</b>
Number of times IIP assignment failed and SNIP is disabled.

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



