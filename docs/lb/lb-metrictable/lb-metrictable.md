#lb metricTable

The following operations can be performed on "lb metricTable":


[add](#add-lb-metrictable) | [rm](#rm-lb-metrictable) | [set](#set-lb-metrictable) | [bind](#bind-lb-metrictable) | [unbind](#unbind-lb-metrictable) | [show](#show-lb-metrictable)

##add lb metricTable

Creates a metric table for load monitoring.


##Synopsys

add lb metricTable &lt;metricTable>


##Arguments

<b>metricTable</b>
Name for the metric table. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my metrictable" or 'my metrictable').



##Example

add metrictable newtable

##rm lb metricTable

Removes a metric table.


##Synopsys

rm lb metricTable &lt;metricTable>


##Arguments

<b>metricTable</b>
Name of the metric table.



##Example

rm metric table netscaler

##set lb metricTable

Modifies the SNMP OID of a metric in a metric table.


##Synopsys

set lb metricTable &lt;metricTable> &lt;metric> &lt;snmpOID>


##Arguments

<b>metricTable</b>
Name of the metric table.

<b>metric</b>
Name of the metric for which to change the SNMP OID.

<b>snmpOID</b>
New SNMP OID of the metric.



##Example

set metrictable table met1 aliasname oidstr

##bind lb metricTable

Binds a metric to a metric table. You must also specify the SNMP OID of the metric.


##Synopsys

bind lb metricTable &lt;metricTable> &lt;metric> &lt;snmpOID>


##Arguments

<b>metricTable</b>
Name of the metric table.

<b>metric</b>
Name of the metric.

<b>snmpOID</b>
SNMP OID of the metric.



##Example

bind metrictable tablename aliasname 1.2.3.4

##unbind lb metricTable

Unbinds a metric from a metric table.


##Synopsys

unbind lb metricTable &lt;metricTable> &lt;metric>


##Arguments

<b>metricTable</b>
Name of the metric table.

<b>metric</b>
Name of the metric to unbind.



##Example

unbind metrictable tablename aliasname

##show lb metricTable

Displays the parameters of the specified metric table. If no metric table name is specified, a list of all configured metric tables is displayed.


##Synopsys

show lb metricTable [&lt;metricTable>]


##Arguments

<b>metricTable</b>
Name of the metric table.



##Outputs

<b>metric</b>
Metric name of the oid.

<b>snmpOID</b>
OID corresponding to the metric

<b>flags</b>
flags controlling display

<b>stateflag</b>
flags controlling display

<b>metricType</b>
Indication if it is a configured or internal

<b>type</b>
Adds a temporary or permanent table.

<b>devno</b>

<b>count</b>



##Example

An example of the show metrictable command output is as follows: Name : ALTEON Type : INTERNAL Name : CISCO-CSS Type : INTERNAL Name : FOUNDRY Type : INTERNAL Name : NETSCALER Type : INTERNAL Name : F5 Type : INTERNAL Name : local Type : INTERNAL

