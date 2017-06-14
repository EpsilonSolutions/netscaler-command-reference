#help

The following operations can be performed on "help":


##help

Use this command to display help information for a CLI command, for a group of commands, or for all CLI commands.


##Synopsys

help [(commandName) | &lt;groupName> | -all]


##Arguments

<b>commandName</b>
The name of a command for which you want full usage information.

<b>groupName</b>
The name of a command group for which you want basic usage information.

<b>all</b>
Use this option to request basic usage information for all commands.



##Example

1.To view help information for adding a virtual server, enter the following CLI command:help add vserverThe following information is displayed:Usage:  add vserver &lt;vServerName&gt; &lt;serviceType&gt; [&lt;IPAddress&gt; port&gt;] [-type ( CONTENT | ADDRESS )] [-cacheType &lt;cacheType&gt;] [-backupVServerName &lt;string&gt;] [-redirectURL &lt;URL&gt;] [-cacheable ( ON | OFF )] [-state ( ENABLED | DISABLED )]where:serviceType = ( HTTP | FTP | TCP | UDP | SSL | SSL_BRIDGE | SSL_TCP | NNTP| DNS | ANY )&lt;cacheType&gt; = ( TRANSPARENT | REVERSE | FORWARD ) Done2.To view help information for all DNS commands, enter the following command:help dnsThe following information is displayed:add aaaaRec &lt;hostname&gt; &lt;IPv6Address&gt; ... [-TTL &lt;secs&gt;]rm aaaaRec &lt;hostname&gt; [&lt;IPv6Address&gt; ...]show aaaaRec [&lt;hostname&gt; |  -type &lt;type&gt;]add addRec &lt;hostname&gt; &lt;IPAddress&gt; ... [-TTL &lt;secs&gt;] [-private &lt;ip_addr&gt;]rm addRec &lt;hostname&gt; [&lt;IPAddress&gt; ...]show addRec [&lt;hostname&gt; |  -type &lt;type&gt;]add cnameRec &lt;aliasName&gt; &lt;canonicalName&gt; [-TTL &lt;secs&gt;]rm cnameRec &lt;aliasName&gt;show cnameRec [&lt;aliasName&gt; |  -type &lt;type&gt;]add mxRec &lt;domain&gt; -mx &lt;string&gt; -pref &lt;positive_integer&gt; [-TTL &lt;secs&gt;]rm mxRec &lt;domain&gt; &lt;mx&gt;set mxRec &lt;domain&gt; -mx &lt;string&gt; [-pref &lt;positive_integer&gt;] [-TTL &lt;secs&gt;]show mxRec [&lt;domain&gt; |  -type &lt;type&gt;]add nsRec &lt;domain&gt; [-p &lt;string&gt;] [-s &lt;string&gt;] [-TTL &lt;secs&gt;]rm nsRec &lt;domain&gt; [-p &lt;string&gt; |  -s &lt;string&gt;]show nsRec [&lt;domain&gt; |  -type &lt;type&gt;]set dns parameter [-timeout &lt;secs&gt;] [-retries &lt;positive_integer&gt;] [-minTTL &lt;secs&gt;] [-maxTTL &lt;secs&gt;] [-TTL ( ENABLED | DISABLED )] [-cacheRecords ( YES | NO )]show dns parameteradd soaRec &lt;domain&gt; -contact &lt;string&gt; -serial &lt;positive_integer&gt; -refresh &lt;secs&gt; -retry &lt;secs&gt; -expire &lt;secs&gt; -minimum &lt;secs&gt;-TTL &lt;secs&gt;rm soaRec &lt;domain&gt;set soaRec &lt;domain&gt; [-contact &lt;string&gt;] [-serial &lt;positive_integer&gt;][-refresh &lt;secs&gt;] [-retry &lt;secs&gt;] [-expire &lt;secs&gt;] [-minimum &lt;secs&gt;][-TTL &lt;secs&gt;]show soaRec [&lt;domain&gt; |  -type &lt;type&gt;]add dns ptrRec &lt;reverseDomain&gt; &lt;domain&gt; ... [-TTL &lt;secs&gt;]rm dns ptrRec &lt;reverseDomain&gt; [&lt;domain&gt; ...]show dns ptrRec [&lt;reverseDomain&gt; | -type &lt;type&gt;]add dns srvRec &lt;domain&gt; &lt;target&gt; -priority &lt;positive_integer&gt;	-weight &lt;positive_integer&gt; -port &lt;positive_integer&gt;rm dns srvRec &lt;domain&gt; [&lt;target&gt; ...]set dns srvRec &lt;domain&gt; &lt;target&gt; [-priority &lt;positive_integer&gt;]	[-weight &lt;positive_integer&gt;] [-port &lt;positive_integer&gt;] [-TTL &lt;secs&gt;]show dns srvRec [(&lt;domain&gt;  [&lt;target&gt;]) | -type &lt;type&gt;]Done

