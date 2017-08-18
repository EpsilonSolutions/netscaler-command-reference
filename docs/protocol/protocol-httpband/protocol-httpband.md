#protocol httpBand

The following operations can be performed on "protocol httpBand":


[set](#set-protocol-httpband) | [unset](#unset-protocol-httpband) | [show](#show-protocol-httpband) | [clear](#clear-protocol-httpband)

##set protocol httpBand

Sets the band size for HTTP request/response band statistics.


##Synopsys

set protocol httpBand [-reqBandSize &lt;integer>] [-respBandSize &lt;integer>]


##Arguments

<b>reqBandSize</b>
Band size, in bytes, for HTTP request band statistics. For example, if you specify a band size of 100 bytes, statistics will be maintained and displayed for the following size ranges:
0 - 99 bytes
100 - 199 bytes
200 - 299 bytes and so on.
Default value: 100
Minimum value: 50

<b>respBandSize</b>
Band size, in bytes, for HTTP response band statistics. For example, if you specify a band size of 100 bytes, statistics will be maintained and displayed for the following size ranges:
0 - 99 bytes
100 - 199 bytes
200 - 299 bytes and so on.
Default value: 1024
Minimum value: 50



##Example

set protocol httpBand -reqBandSize 200 -respBandSize 2048

##unset protocol httpBand

Use this command to remove protocol httpBand settings.Refer to the set protocol httpBand command for meanings of the arguments.


##Synopsys

unset protocol httpBand [-reqBandSize] [-respBandSize]


##show protocol httpBand

Displays statistics of the HTTP request/response band.


##Synopsys

show protocol httpBand -type ( REQUEST | RESPONSE )


##Arguments

<b>type</b>
Type of statistics to display.
Possible values: REQUEST, RESPONSE



##Outputs

<b>BandRange</b>
The range of the HTTP request/response size, in bytes.

<b>numberofbands</b>
The total number of http bands.

<b>TotalBandSize</b>
The total size of all HTTP requests/responses in this size range.

<b>AvgBandSize</b>
The average size of all HTTP requests/responses in this size range.

<b>AvgBandSizeNew</b>
The average size of all HTTP requests/responses in this size range.

<b>BandData</b>
The total size of all HTTP requests/responses in this size range, expressed as a percentage of the total size of all HTTP requests/responses.

<b>BandDataNew</b>
The total size of all HTTP requests/responses in this size range, expressed as a percentage of the total size of all HTTP requests/responses.

<b>AccessCount</b>
The number of HTTP requests/responses in this size range.

<b>AccessRatio</b>
The number of HTTP requests/responses in this size range, expressed as a percentage of the total number of HTTP requests/responses.

<b>AccessRatioNew</b>
The number of HTTP requests/responses in this size range, expressed as a percentage of the total number of HTTP requests/responses.

<b>Totals</b>
The total of totalBandSize, avgBandSize, BandData, accessCount, accessRatio respectively.

<b>reqBandSize</b>
Band size, in bytes, for HTTP request band statistics. For example, if you specify a band size of 100 bytes, statistics will be maintained and displayed for the following size ranges:
0 - 99 bytes
100 - 199 bytes
200 - 299 bytes and so on.

<b>respBandSize</b>
Band size, in bytes, for HTTP response band statistics. For example, if you specify a band size of 100 bytes, statistics will be maintained and displayed for the following size ranges:
0 - 99 bytes
100 - 199 bytes
200 - 299 bytes and so on.



##clear protocol httpBand

Clears HTTP request/response band statistics.


##Synopsys

clear protocol httpBand -type ( REQUEST | RESPONSE )


##Arguments

<b>type</b>
Type of statistics to display.
Possible values: REQUEST, RESPONSE



##Example

clear protocol httpband -type REQUEST, clear protocol httpband -type RESPONSE

