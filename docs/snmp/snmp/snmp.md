#snmp

The following operations can be performed on "snmp":


##stat snmp

Display the statistics related to SNMP.


##Synopsys

stat snmp [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


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

<b>SNMP packets received (PktsRx)</b>
SNMP packets received.

<b>SNMP packets sent (PktsTx)</b>
SNMP packets transmitted.

<b>Get requests receieved (GetReqRx)</b>
SNMP Get-Request PDUs that have been accepted and processed.

<b>Get-next requests receieved (GtNextRx)</b>
SNMP Get-Next PDUs that have been accepted and processed.

<b>Get-bulk requests received (GtBulkRx)</b>
SNMP Get-Bulk PDUs that have been accepted and processed.

<b>Responses sent (RspTx)</b>
SNMP Get-Response PDUs that have been generated by the NetScaler.

<b>Traps messages sent (TrapsTx)</b>
SNMP Trap PDUs that have been generated by the NetScaler.

<b>Requests dropped (ReqDrop)</b>
SNMP requests dropped.

<b>ASN.1/BER errors in requests (PrsErrRx)</b>
Number of ASN.1 or BER errors encountered when decoding received SNMP Messages.

<b>Unsupported SNMP version (UnkVrsRx)</b>
Number of SNMP messages received, which were for an unsupported SNMP version.

<b>Unknown community name (UnkCNRx)</b>
SNMP messages received, which used an SNMP community name not known to the NetScaler.

<b>No permission on community (BadCURx)</b>
The total number of SNMP Messages received that represented an SNMP operation which was not allowed by the SNMP community named in the Message.

<b>Unsupported security level (UnkSecLv)</b>
SNMP packets that were dropped because they requested a security level that was
unknown to the NetScaler or otherwise unavailable.

<b>Not in time window (NtTimeWd)</b>
SNMP packets that were dropped because they appeared outside of the authoritative SNMP engine's window.

<b>Unknown user name (UnkUser)</b>
SNMP packets that were dropped because they referenced a user that was  not  known to the SNMP engine.

<b>Unknown engine Id (UnkEngId)</b>
SNMP packets that were dropped because they referenced an SNMP engine ID that was not known to the NetScaler.

<b>Wrong digest value (WrgDgst)</b>
SNMP packets that were dropped because they did not contain the expected digest value.

<b>Decryption errors (DcrptErr)</b>
SNMP packets that were dropped because they could not be decrypted.



##Example

stat snmp

