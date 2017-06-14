#appqoe

The following operations can be performed on "appqoe":


##stat appqoe

Displays statistics of feature AppQoE.


##Synopsys

stat appqoe [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>In-Memory responses sent (TotInMemRsp)</b>
Total in-memory responses sent from NS

<b>Faulty cookies received (TotFaultyCookies)</b>
Total faulty cookies received

<b>Valid cookies received (TotValidCookies)</b>
Total valid cookies received

<b>High priority requests served (TotHighPriReq)</b>
Total Requests served from higher priority queue

<b>Medium priority requests served (TotMediumPriReq)</b>
Total Requests served from medium priority queue

<b>Low priority requests served (TotLowPriReq)</b>
Total Requests served from low priority queue

<b>Lowest(Surge) priority requests served (TotLowestPriReq)</b>
Total Requests served from surge priority queue

<b>Alt. server substitution failed (TotAltSvrSubFailed)</b>
Total number of times alternate server substitution failed

<b>HDOS condition triggered (TotDoSTrig)</b>
Total number of times HDOS condition triggered

<b>Valid DOSQ cookies received (TotDOSQValidCookies)</b>
Total DOSQ valid cookies received

<b>Valid DOSH cookies received (TotDOSHValidCookies)</b>
Total DOSH valid cookies received

<b>Valid SID cookies received (TotSIDValidCookies)</b>
Total SID valid cookies received

<b>Valid ONH cookies received (TotONHValidCookies)</b>
Total ONH valid cookies received

<b>Valid PRIQ cookies received (TotPRIQValidCookies)</b>
Total PRIQ valid cookies received

<b>Faulty DOSQ cookies received (TotDOSQFaultyCookies)</b>
Total DOSQ faulty cookies received

<b>Faulty DOSH cookies received (TotDOSHFaultyCookies)</b>
Total DOSH faulty cookies received

<b>Faulty SID cookies received (TotSIDFaultyCookies)</b>
Total SID faulty cookies received

<b>Faulty ONH cookies received (TotONHFaultyCookies)</b>
Total ONH faulty cookies received

<b>Faulty PRIQ cookies received (TotPRIQFaultyCookies)</b>
Total PRIQ faulty cookies received

<b>Requests for valid embedded links (TotPRIEmbedLinks)</b>
Total requests for valid embedded links

<b>Valid SIDQ req. within session (TotSessReq)</b>
Total valid SIDQ requests within session

<b>Requests for alternate contents (TotAltCntReq)</b>
Total requests for alternate contents

<b>In-Memory GET responses sent (TotGETInMemRsp)</b>
Total in-memory GET responses sent from NS

<b>In-Memory POST responses sent (TotPOSTInMemRsp)</b>
Total in-memory POST responses sent from NS

<b>In-Memory response bytes sent (TotInMemRspbytes)</b>
Total in-memory response bytes sent from NS



##Related Commands

<ul><li><a href="../../../l#stat-appqoe-p/l#stat-appqoe-p">stat appqoe policy</a></li></ul>



