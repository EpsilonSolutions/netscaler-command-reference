#appfw

The following operations can be performed on "appfw":


##stat appfw

Displays application firewall statistics.


##Synopsys

stat appfw [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>total violations (totviols)</b>
Total number of security check violations seen by the Application Firewall.

<b>Recent Ave Response Time (ms) (shortAvgRespTime)</b>
Average backend response time in milliseconds over the last 7 seconds

<b>Long Term Ave Response Time (ms) (longAvgRespTime)</b>
Average backend response time in milliseconds since reboot

<b>requests (reqs)</b>
HTTP/HTTPS requests sent to your protected web servers via the Application Firewall.

<b>Request Bytes (reqBytes)</b>
Number of bytes transfered for requests

<b>responses (resps)</b>
HTTP/HTTPS responses sent by your protected web servers via the Application Firewall.

<b>Response Bytes (resBytes)</b>
Number of bytes transfered for responses

<b>aborts</b>
Incomplete HTTP/HTTPS requests aborted by the client before the Application Firewall could finish processing them.

<b>redirects (redirect)</b>
HTTP/HTTPS requests redirected by the Application Firewall to a different Web page or web server. (HTTP 302)

<b>Traps Dropped (trapsDr)</b>
AppFirewall SNMP traps dropped due to time limit.

<b>start URL (startURL)</b>
Number of Start URL security check violations seen by the Application Firewall.

<b>deny URL (denyURL)</b>
Number of Deny URL security check violations seen by the Application Firewall.

<b>referer header (refererHdr)</b>
Number of Referer Header security check violations seen by the Application Firewall.

<b>buffer overflow (bufovfl)</b>
Number of Buffer Overflow security check violations seen by the Application Firewall.

<b>cookie consistency (cookie)</b>
Number of Cookie Consistency security check violations seen by the Application Firewall.

<b>CSRF form tag (csrf_tag)</b>
Number of Cross Site Request Forgery form tag security check violations seen by the Application Firewall.

<b>HTML Cross-site scripting (xss)</b>
Number of HTML Cross-Site Scripting security check violations seen by the Application Firewall.

<b>HTML SQL injection (sql)</b>
Number of HTML SQL Injection security check violations seen by the Application Firewall.

<b>field format (fieldfmt)</b>
Number of Field Format security check violations seen by the Application Firewall.

<b>field consistency (fieldcon)</b>
Number of Field Consistency security check violations seen by the Application Firewall.

<b>credit card (ccard)</b>
Number of Credit Card security check violations seen by the Application Firewall.

<b>safe object (safeobj)</b>
Number of Safe Object security check violations seen by the Application Firewall.

<b>Signature Violations (sigs)</b>
Number of Signature violations seen by the Application Firewall.

<b>XML Format (wfcViolations)</b>
Number of XML Format security check violations seen by the Application Firewall.

<b>XML Denial of Service (XDoS) (xdosViolations)</b>
Number of XML Denial-of-Service security check violations seen by the Application Firewall.

<b>XML Message Validation (msgvalViolations)</b>
Number of XML Message Validation security check violations seen by the Application Firewall.

<b>Web Services Interoperability (wsIViolations)</b>
Number of Web Services Interoperability (WS-I) security check violations seen by the Application Firewall.

<b>XML SQL Injection (xmlSqlViolations)</b>
Number of XML SQL Injection security check violations seen by the Application Firewall.

<b>XML Cross-Site Scripting (xmlXssViolations)</b>
Number of XML Cross-Site Scripting (XSS) security check violations seen by the Application Firewall.

<b>XML Attachment (xmlAttachmentViolations)</b>
Number of XML Attachment security check violations seen by the Application Firewall.

<b>SOAP Fault Violations (soapflt)</b>
Number of requests returning soap:fault from the backend server

<b>XML Generic Violations (genflt)</b>
Number of requests returning XML generic error from the backend server

<b>HTTP Client Errors (4xx Resp) (4xxResps)</b>
Number of requests returning HTTP 4xx from the backend server

<b>HTTP Server Errors (5xx Resp) (5xxResps)</b>
Number of requests returning HTTP 5xx from the backend server



##Related Commands

<ul><li><a href="../../../#stat-appfw-pr/#stat-appfw-pr">stat appfw profile</a></li><li><a href="../../../stat-appfw-p/stat-appfw-p">stat appfw policy</a></li><li><a href="../../../html#stat-appfw-policy/html#stat-appfw-policy">stat appfw policylabel</a></li></ul>



