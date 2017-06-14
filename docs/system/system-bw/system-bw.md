#system bw

The following operations can be performed on "system bw":


##stat system bw

Displays BW statistics


##Synopsys

stat system bw [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>Number of HTTP Requests Sent (httpClttotpoolinactive)</b>
No of requests sent from BW client.

<b>Number of HTTP responses received (httpClttotpooloutactive)</b>
No of responses Received.

<b>Http responses (200 OK) (httpSvr200OKresp)</b>
Number of 200 Ok response sent from the BW appliance.

<b>Http response error (404 NotFound) (httpSvr404ObjNotFound)</b>
Number of 404 Not Found responses sent

<b>No of stray packets received without request (httpClterrstray)</b>
Number of stray packets received from server without HTTP request

<b>RTT Value < 0.5 ms (httpCltTTFPBandLWM)</b>
Number of Responses Falling on LWM for TTFP.

<b>RTT Value > 0.5 ms AND <= 1.5 ms (httpCltTTFPBand0)</b>
Number of Responses Falling on Band-0 for TTFP.

<b>RTT Value > 1.5 ms AND <= 2.5 ms (httpCltTTFPBand1)</b>
Number of Responses Falling on Band-1 for TTFP.

<b>RTT Value > 2.5 ms AND <= 3.5 ms (httpCltTTFPBand2)</b>
Number of Responses Falling on Band-2 for TTFP.

<b>RTT Value > 3.5 ms AND <= 4.5 ms (httpCltTTFPBand3)</b>
Number of Responses Falling on Band-3 for TTFP.

<b>RTT Value > 4.5 ms AND <= 5.5 ms (httpCltTTFPBand4)</b>
Number of Responses Falling on Band-4 for TTFP.

<b>RTT Value > 5.5 ms AND <= 6.5 ms (httpCltTTFPBand5)</b>
Number of Responses Falling on Band-5 for TTFP.

<b>RTT Value > 6.5 ms AND <= 7.5 ms (httpCltTTFPBand6)</b>
Number of Responses Falling on Band-6 for TTFP.

<b>RTT Value > 7.5 ms AND <= 8.5 ms (httpCltTTFPBand7)</b>
Number of Responses Falling on Band-7 for TTFP.

<b>RTT Value > 8.5 ms (httpCltTTFPBandHWM)</b>
Number of Responses Falling on HWM for TTFP.

<b>TTFP Peak RTT (httpCltTTFPMax)</b>
Peak RTT observed for Time to First response packet.

<b>RTT Value < 0.5 ms (httpCltTTLPBandLWM)</b>
Number of Responses Falling on LWM for TTLP.

<b>RTT Value > 0.5 ms AND <= 1.5 ms (httpCltTTLPBand0)</b>
Number of Responses Falling on Band-0 for TTLP.

<b>RTT Value > 1.5 ms AND <= 2.5 ms (httpCltTTLPBand1)</b>
Number of Responses Falling on Band-1 for TTLP.

<b>RTT Value > 2.5 ms AND <= 3.5 ms (httpCltTTLPBand2)</b>
Number of Responses Falling on Band-2 for TTLP.

<b>RTT Value > 3.5 ms AND <= 4.5 ms (httpCltTTLPBand3)</b>
Number of Responses Falling on Band-3 for TTLP.

<b>RTT Value > 4.5 ms AND <= 5.5 ms (httpCltTTLPBand4)</b>
Number of Responses Falling on Band-4 for TTLP.

<b>RTT Value > 5.5 ms AND <= 6.5 ms (httpCltTTLPBand5)</b>
Number of Responses Falling on Band-5 for TTLP.

<b>RTT Value > 6.5 ms AND <= 7.5 ms (httpCltTTLPBand6)</b>
Number of Responses Falling on Band-6 for TTLP.

<b>RTT Value > 7.5 ms AND <= 8.5 ms (httpCltTTLPBand7)</b>
Number of Responses Falling on Band-7 for TTLP.

<b>RTT Value > 8.5 ms (httpCltTTLPBandHWM)</b>
Number of Responses Falling on HWM for TTLP.

<b>TTLP peak RTT (httpCltTTLPMax)</b>
Peak RTT observed for Time to Last response packet.



##Related Commands

<ul><li><a href="../../../s/s">stat system</a></li><li><a href="../../../tat-syste/tat-syste">stat system cpu</a></li><li><a href="../../../l#stat-system-m/l#stat-system-m">stat system memory</a></li></ul>



