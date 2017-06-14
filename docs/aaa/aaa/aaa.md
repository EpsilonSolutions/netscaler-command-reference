#aaa

The following operations can be performed on "aaa":


##stat aaa

Display aaa statistics


##Synopsys

stat aaa [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>clearstats</b>
Clear the statsistics / counters Possible values: basic, full



##Outputs

<b>Authentication successes (authsucc)</b>
Count of authentication successes.

<b>Authentication failures (authfails)</b>
Count of authentication failures.

<b>HTTP authorization successes (atzhtps)</b>
Count of HTTP connections that succeeded authorization.

<b>HTTP authorization failures (atzhtpf)</b>
Count of HTTP connections that failed authorization.

<b>Non HTTP authorization successes (atznonhtps)</b>
Count of non HTTP connections that succeeded authorization.

<b>Non HTTP authorization failures (atznonhtpf)</b>
Count of non HTTP connections that failed authorization.

<b>Current AAA sessions (totcursess)</b>
Count of current AAA sessions.

<b>Total AAA sessions (totsess)</b>
Count of all AAA sessions.

<b>Timed out AAA sessions (totsessto)</b>
Count of AAA sessions that have timed out.

<b>Current ICAOnly sessions (totcuricasess)</b>
Count of current ICA only sessions.

<b>Current ICAOnly Conn (curicaonlyconn)</b>
Count of current ICA only connections.

<b>Current ICA (Smart Access) Conn (curicaconn)</b>
Count of current ICA connections.

<b>Current TM sessions (curTMses)</b>
Count of current AAATM sessions.

<b>TM sessions (totTMses)</b>
Count of all AAATM sessions.



