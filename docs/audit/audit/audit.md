#audit

The following operations can be performed on "audit":


##stat audit

Display the audit statistics


##Synopsys

stat audit [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>Audit logs sent to syslog server(s) (LogSnd)</b>
Syslog messages sent to the syslog server(s).

<b>Audit log messages generated (LogGen)</b>
Syslog messages about to be sent to the syslog server.

<b>NAT allocation failed (Ernatpcb)</b>
NAT allocation failed.

<b>Nsb allocation failed (Ernsb)</b>
Nsb allocation failed.

<b>Memory allocation failed (Ermem)</b>
Failures in allocation of Access Gateway context structure. When an Access Gateway session is established, the NetScaler creates an internal context structure , which identifies the user and the IP address from which the user has logged in.

<b>Port allocation failed (Erport)</b>
Number of times the NetScaler failed to allocate a port when sending a syslog message to the syslog server(s).

<b>NAT lookup failed (Hshmiss)</b>
NAT lookup failed.

<b>Context not found (Ctxntfnd)</b>
Failures in finding the context structure for an Access Gateway session during attempts to send session-specific audit messages.
During an Access Gateway session, audit messages related to the session are queued up in the auditlog buffer for transmission to the audit log server(s). If the session is killed before the messages are sent, the context structure allocated at session creation is removed. This structure is needed for sending the queued auditlog messages. If it is not found, this counter is incremented.

<b>Nsb chain allocation failed (Ernsbchn)</b>
Nsb Chain allocation failed.

<b>Client connect failed (Erclconn)</b>
Failures in establishment of a connection between the NetScaler and the auditserver tool (the Netscaler's custom logging tool).

<b>MP buffer flush command count (flcmdcnt)</b>
Auditlog buffer flushes. In a multiprocessor NetScaler, both the main processor and the co-processor can generate auditlog messages and fill up the auditlog buffers. But only the primary processor can free up the buffers by sending auditlog messages to the auditlog server(s). The number of auditlog buffers is fixed. If the co-processor detects that all the auditlog buffers are full, it issues a flush command to the main processor.



