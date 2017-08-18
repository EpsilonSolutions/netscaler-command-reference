#qos

The following operations can be performed on "qos":


##stat qos

Display QoS statistics.


##Synopsys

stat qos [-name ] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>

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

<b>Receive direction packets processed by QoS (qos_packets_received)</b>
Receive direction packets processed by QoS

<b>Send direction packets processed by QoS (qos_packets_sent)</b>
Send direction packets processed by QoS

<b>Packets bypassing QoS (qos_packets_bypassed)</b>
Packets bypassing QoS

<b>Total packets dropped (qos_packets_dropped)</b>
Total packets dropped

<b>Received bytes processed by QoS (qos_bytes_rx)</b>
Received bytes processed by QoS

<b>Sent bytes processed by QoS (qos_bytes_tx)</b>
Sent bytes processed by QoS

<b>QoS lazy byte optimization rate (qos_lazy_bytes)</b>
QoS lazy byte optimization rate

<b>QoS actual bytes scheduled (qos_real_bytes)</b>
QoS actual bytes scheduled

<b>Total packets filtered by QoS (qos_packets_filtered)</b>
Total packets filtered by QoS

<b>Total packets classified by QoS (qos_packets_classified)</b>
Total packets classified by QoS

<b>New QoS flows (qos_flows)</b>
New QoS flows

<b>Recycled QoS flows (qos_flow_recycles)</b>
Recycled QoS flows

<b>QoS Flow Recycle failures (qos_session_recycle_failure)</b>
QoS Flow Recycle failures

<b>Sessions manually ignored (qos_sessions_ignored)</b>
Sessions manually ignored

<b>sessions manually consumed (qos_sessions_consumed)</b>
sessions manually consumed

<b>Uneque qos action objects created (qos_actions_created)</b>
Uneque qos action objects created

<b>Policies re-evaluated due to cli change (qos_policy_reeval)</b>
Policies re-evaluated due to cli change

<b>Connections unable to be classified beyond TCP (qos_cfy_tcp_unknown)</b>
Connections unable to be classified beyond TCP

<b>Connections unable to be classified beyond UDP (qos_cfy_udp_unknown)</b>
Connections unable to be classified beyond UDP

<b>Scheduler leaf nodes constructed (qos_sch_leafs)</b>
Scheduler leaf nodes constructed

<b>Scheduler nodes constructed (qos_session_mem)</b>
Scheduler nodes constructed

<b>Scheduler virtual packets constructed (qos_sch_virtual_packets)</b>
Scheduler virtual packets constructed

<b>Scheduler bytes accepted (qos_sch_virtual_bytes_accepted)</b>
Scheduler bytes accepted

<b>Scheduler Failures to recycle QoS flows (qos_sch_leaf_recycle_failures)</b>
Scheduler Failures to recycle QoS flows

<b>Scheduler Regulated node count (qos_sch_node_regulated_count)</b>
Scheduler Regulated node count

<b>Scheduler session classes constructed (qos_sch_sessions_created)</b>
Scheduler session classes constructed

<b>Scheduler session classes constructed (qos_sch_sessions_deleted)</b>
Scheduler session classes constructed

<b>Scheduler sdrr nodes constructed (qos_sch_sdrr_nodes)</b>
Scheduler sdrr nodes constructed

<b>Scheduler session connections created (qos_sch_session_conns)</b>
Scheduler session connections created

<b>Scheduler session connections removed (qos_sch_session_conns_removed)</b>
Scheduler session connections removed

<b>Scheduler regulated sessions count (qos_sch_sessions_regulated_count)</b>
Scheduler regulated sessions count

<b>Scheduler session bytes total (qos_sch_sessions_byte_count)</b>
Scheduler session bytes total

<b>Scheduler regulated node count (qos_sch_regulated_count)</b>
Scheduler regulated node count

<b>Scheduler links created (qos_sch_links_created)</b>
Scheduler links created

<b>Scheduler links deleted (qos_sch_links_deleted)</b>
Scheduler links deleted

<b>Scheduler links updated (qos_sch_links_updated)</b>
Scheduler links updated

<b>Scheduler calls to poll_libqos (qos_sch_poll_count)</b>
Scheduler calls to poll_libqos

<b>Scheduler peer messages received (qos_sch_peer_msgs)</b>
Scheduler peer messages received

<b>IPC failed for QoS messages. (qos_error_ipc)</b>
IPC failed for QoS messages.

<b>DPI inspection state invalid (qos_flow_mem)</b>
DPI inspection state invalid

<b>recycel failed backlog (qos_recycle_failed_backlog)</b>
recycle failed backlog

<b>qos recycle failures due to session (qos_recycle_failed_session)</b>
qos recycle failures because of associated session

<b>Failed attempts to create actions (qos_error_create_action_failed)</b>
Failed attempts to create actions

<b>Failed attempts to modify actions (qos_error_modify_action_failed)</b>
Failed attempts to modify actions

<b>Failed attempts to remove actions (qos_error_remove_action_failed)</b>
Failed attempts to remove actions

<b>Internal CLI error (qos_error_cli_unknown)</b>
Internal CLI error

<b>qos action rename not yet implemented (qos_error_rename_not_implemented)</b>
qos action rename not yet implemented

<b>Failed attempts to remove qos policy (qos_error_remove_policy_failed)</b>
Failed attempts to remove qos policy

<b>Failed attempts to create qos policy (qos_error_create_policy_failed)</b>
Failed attempts to create qos policy

<b>Libqos api failures (qos_error_libqos_api_failures)</b>
Libqos api failures

<b>Libqos api qos_session_add_pcb/natpcb() failed for reason QS_EINVALIDPCB (qos_error_api_ses_invalidpcb)</b>
Libqos api qos_session_add_pcb/natpcb() failed for reason QS_EINVALIDPCB

<b>Libqos api qos_session_add_pcb/natpcb() failed for reason QS_ENOTREADY (qos_error_api_ses_notready)</b>
Libqos api qos_session_add_pcb/natpcb() failed for reason QS_ENOTREADY

<b>Libqos api qos_session_add_pcb/natpcb() failed for reason QS_EINSESSION (qos_error_api_ses_add_insession)</b>
Libqos api qos_session_add_pcb/natpcb() failed for reason QS_EINSESSION

<b>Libqos api qos_session_add_pcb/natpcb() failed (qos_error_api_ses_add_other)</b>
Libqos api qos_session_add_pcb/natpcb() failed

<b>Libqos api qos_session_rem_pcb/natpcb() failed for reason QS_ENOTINSESSION (qos_error_api_ses_rem_notinsession)</b>
Libqos api qos_session_rem_pcb/natpcb() failed for reason QS_ENOTINSESSION

<b>Libqos api qos_session_rem_pcb/natpcb() failed (qos_error_api_ses_rem_other)</b>
Libqos api qos_session_rem_pcb/natpcb() failed

<b>Libqos api qos_session_delete faled (qos_error_api_ses_del)</b>
Libqos api qos_session_delete faled



