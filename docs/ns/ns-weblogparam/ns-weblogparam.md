#ns weblogparam

The following operations can be performed on "ns weblogparam":


[set](#set-ns-weblogparam) | [unset](#unset-ns-weblogparam) | [show](#show-ns-weblogparam)

##set ns weblogparam

Sets the Weblog parameters.


##Synopsys

set ns weblogparam [-bufferSizeMB &lt;positive_integer>] [-customReqHdrs &lt;string> ...] [-customRspHdrs &lt;string> ...]


##Arguments

<b>bufferSizeMB</b>
Buffer size, in MB, allocated for log transaction data on the system. The maximum value is limited to the memory available on the system.
Default value: 16
Minimum value: 1
Maximum value: 4294967294LU

<b>customReqHdrs</b>
Name(s) of HTTP request headers whose values should be exported by the Web Logging feature.

<b>customRspHdrs</b>
Name(s) of HTTP response headers whose values should be exported by the Web Logging feature.



##unset ns weblogparam

Use this command to remove ns weblogparam settings.Refer to the set ns weblogparam command for meanings of the arguments.


##Synopsys

unset ns weblogparam [-bufferSizeMB] [-customReqHdrs] [-customRspHdrs]


##show ns weblogparam

Displays the Weblog parameters.


##Synopsys

show ns weblogparam


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>bufferSizeMB</b>
Buffer size in MB.

<b>customReqHdrs</b>
Name(s) of HTTP request headers whose values should be exported by the Web Logging feature.

<b>customRspHdrs</b>
Name(s) of HTTP response headers whose values should be exported by the Web Logging feature.



