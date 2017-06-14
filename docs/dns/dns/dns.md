#dns

The following operations can be performed on "dns":


##stat dns

Displays DNS statistics.


##Synopsys

stat dns [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>Dns queries (Q)</b>
Total number of DNS queries received.

<b>Multi queries (MtQ)</b>
Total number of Multi Query request received.

<b>Dns responses (Rsp)</b>
Total number of DNS responses received.

<b>Server responses (SvrRsp)</b>
Total number of Server responses received.

<b>Total Record updates (TotRecUp)</b>
Total number of record updates.

<b>Auth answers (AuthAns)</b>
Number of queries which were authoritatively answered.

<b>Server queries (SvrQ)</b>
Total number of Server queries sent.

<b>Cache flush called (CaFsh)</b>
Total number of times cache was flushed.

<b>Cache entries flushed (CaEntFsh)</b>
Total number of cache entries flushed.

<b>Non-authoritative entries (PxyEnt)</b>
Total number of non-authoritative entries.

<b>Authoritative entries (AthEnt)</b>
Total number of authoritative entries.

<b>Nonexistent domain (NoDomain)</b>
Number of queries for which no record was found.

<b>Response class unsupported (RspClsEr)</b>
Total number of responses for which response types were unsupported.

<b>Invalid query format (InQFmt)</b>
Total number of queries whose format was invalid.

<b>Stray answers (StryRsp)</b>
Total number of stray answers.

<b>Incorrect RD length (BadRDlen)</b>
Number of DNS responses received with invalid resoure data length.

<b>Requests refused (ReqRefused)</b>
Number of DNS requests refused.

<b>NULL Attack (NullAttack)</b>
Total number of queries received where all the counts are 0.

<b>Response type unsupported (RspNoSup)</b>
Total number of responses for which response type requested was unsupported.

<b>Query class unsupported (QClsEr)</b>
Total number of queries for which query class was unsupported.

<b>Invalid response format (InRspFmt)</b>
Total number of responses for which there was a format error.

<b>No answer responses (NoAnswer)</b>
Number of DNS responses received without answer.

<b>Multi queries disabled (MtQErr)</b>
Total number of times a multi query was disabled and received a multi query.

<b>Other errors (OtherErr)</b>
Total number of other errors.

<b>DNS64 queries</b>
Total number of DNS64 queries recieved.

<b>DNS64 answers</b>
Total number of DNS64 answers served.

<b>DNS64 rewrite answers</b>
Total number of DNS64 answers served after rewriting the response.

<b>DNS64 responses</b>
Total number of responses recieved from backend in DNS64 context.

<b>DNS64 GSLB Queries</b>
Total number of DNS64 queries for GSLB domain

<b>DNS64 GSLB Answers</b>
Total number of DNS64 queries served.

<b>DNS64 Total truncated answers</b>
Total number of Answers served with TC bit set in DNS64 context.

<b>DNS64 Total A queries to server</b>
Total number of Queries sent by DNS64 module to backend.

<b>DNS64 Total times AAAA query bypassed</b>
Total number of times AAAA query has been bypassed in DNS64 trnsaction.

<b>DNS64 Total TCP  queries</b>
Total number of dns64 queries over TCP

<b>DNS64 Total Active policies</b>
Total number of active dns64 policies

<b>DNS64 Total NODATA Responses</b>
Total number of responses recieved from backend with ancount 0

<b>NS queries (NSQ)</b>
Total number of NS queries received.

<b>SOA queries (SOAQ)</b>
Total number of SOA queries received.

<b>PTR queries (PTRQ)</b>
Total number of PTR queries received.

<b>SRV queries (SRVQ)</b>
Total number of SRV queries received.

<b>A responses (ARsp)</b>
Total number of A responses received.

<b>CNAME responses (CNRsp)</b>
Total number of CNAME responses received.

<b>MX responses (MXRsp)</b>
Total number of MX responses received.

<b>ANY responses (ANYRsp)</b>
Total number of ANY responses received.

<b>NS updates (NSUp)</b>
Total number of NS record updates.

<b>SOA updates (SOAUp)</b>
Total number of SOA record updates.

<b>PTR updates (PTRUp)</b>
Total number of PTR record updates.

<b>SRV updates (SRVUp)</b>
Total number of SRV record updates.

<b>AAAA queries (AAAAQ)</b>
Total number of AAAA queries received.

<b>A queries (AQ)</b>
Total number of A queries received.

<b>CNAME queries (CNQ)</b>
Total number of CNAME queries received.

<b>MX queries (MXQ)</b>
Total number of MX queries received.

<b>ANY queries (ANYQ)</b>
Total number of ANY queries received.

<b>AAAA responses (AAAARsp)</b>
Total number of AAAA responses received.

<b>NS responses (NSRsp)</b>
Total number of NS responses received.

<b>SOA responses (SOARsp)</b>
Total number of SOA responses received.

<b>PTR responses (PTRRsp)</b>
Total number of PTR responses received.

<b>SRV responses (SRVRsp)</b>
Total number of SRV responses received.

<b>AAAA updates (AAAAUp)</b>
Total number of AAAA record updates.

<b>A updates (AUp)</b>
Total number of A record updates.

<b>MX updates (MXUp)</b>
Total number of MX record updates.

<b>CNAME updates (CNUp)</b>
Total number of CNAME record updates.

<b>AAAA records (AAAARec)</b>
Total number of AAAA records.

<b>A records (ARec)</b>
Total number of A records.

<b>MX records (MXRec)</b>
Total number of MX records.

<b>CNAME records (CNRec)</b>
Total number of CNAME records.

<b>NS records (NSRec)</b>
Total number of NS records.

<b>SOA records (SOARec)</b>
Total number of SOA records.

<b>PTR records (PTRRec)</b>
Total number of PTR records.

<b>SRV records (SRVRec)</b>
Total number of SRV records.

<b>No AAAA records (NoAAAARec)</b>
Total number of times AAAA record lookup failed.

<b>No A records (NoARec)</b>
Total number of times A record lookup failed.

<b>No MX records (NoMXRec)</b>
Total number of times MX record lookup failed.

<b>No PTR records (NoPTRRec)</b>
Total number of times PTR record lookup failed.

<b>No NS records (NoNSRec)</b>
Total number of times NS record lookup failed.

<b>No CNAME records (NoCNRec)</b>
Total number of times CNAME record lookup failed.

<b>No SOA records (NoSOARec)</b>
Total number of times SOA record lookup failed.

<b>No SRV records (NoSRVRec)</b>
Total number of times SRV record lookup failed.

<b>No ANY records (NoANYrec)</b>
Total number of times ANY query lookup failed.

<b>Unsupported queries (NotSupQ)</b>
Total number of requests for which query type requested was unsupported.



##Related Commands

<ul><li><a href="../../../t-dns-re/t-dns-re">stat dns records</a></li><li><a href="../../../#stat-dns-policy/#stat-dns-policy">stat dns policylabel</a></li></ul>



