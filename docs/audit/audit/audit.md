#audit

The following operations can be performed on "audit":


##stat audit

Display the audit statistics


##Synopsys

stat audit [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


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

<b>Logs sent to syslog server(UDP) (LogSnd)</b>
Syslog messages sent to the syslog server(s) over UDP.

<b>Audit log messages generated (LogGen)</b>
Syslog messages about to be sent to the syslog server.

<b>Logs sent to syslog server(TCP) (LogSndTcp)</b>
Syslog messages sent to the syslog server(s) over TCP.

<b>NAT allocation failed (Ernatpcb)</b>
NAT allocation failed.

<b>Nsb allocation failed (Ernsb)</b>
Nsb allocation failed.

<b>Memory allocation failed (Ermem)</b>
Failures in allocation of Access Gateway context structure. When an Access Gateway session is established, the NetScaler creates an internal context structure , which identifies the user and the IP address from which the user has logged in.

<b>Port allocation failed (Erport)</b>
Number of times the NetScaler failed to allocate a port when sending a syslog message to the syslog server(s).

<b>Context not found (Ctxntfnd)</b>
Failures in finding the context structure for an Access Gateway session during attempts to send session-specific audit messages.
During an Access Gateway session, audit messages related to the session are queued up in the auditlog buffer for transmission to the audit log server(s). If the session is killed before the messages are sent, the context structure allocated at session creation is removed. This structure is needed for sending the queued auditlog messages. If it is not found, this counter is incremented.

<b>Nsb chain allocation failed (Ernsbchn)</b>
Nsb Chain allocation failed.

<b>Client connect failed (Erclconn)</b>
Failures in establishment of a connection between the NetScaler and the auditserver tool (the Netscaler's custom logging tool).

<b>MP buffer flush command count (flcmdcnt)</b>
Auditlog buffer flushes. In a multiprocessor NetScaler, both the main processor and the co-processor can generate auditlog messages and fill up the auditlog buffers. But only the primary processor can free up the buffers by sending auditlog messages to the auditlog server(s). The number of auditlog buffers is fixed. If the co-processor detects that all the auditlog buffers are full, it issues a flush command to the main processor.

<b>TCP connect failed for syslog (Ersystcpconn)</b>
Failures in establishment of a connection between the NetScaler and the syslog server.

<b>Logs unsent to LB syslog server (LogUnsentLBsys)</b>
Total auditlog messages which are not delivered to load balanced syslog servers

<b>Logs dropped(max hold limit) (DroppedLogsCnt)</b>
Total number of log messages dropped by NetScaler after max hold limit is reached

<b>Logs dropped(TX min NSBS) (DroppedLogsCntTxMinNSBs)</b>
Total number of log messages dropped by NetScaler when NSBQ length is less than TX min NSBs



