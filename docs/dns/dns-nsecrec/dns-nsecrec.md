#dns nsecRec

The following operations can be performed on "dns nsecRec":


##show dns nsecRec

Displays the NextSECure (NSEC) resource records created for the specified domain name.


##Synopsys

show dns nsecRec [&lt;hostName> | -type &lt;type>]


##Arguments

<b>hostName</b>
Name of the domain.

<b>type</b>
Type of records to display. Available settings function as follows:
* ADNS - Display all authoritative address records.
* PROXY - Display all proxy address records.
* ALL - Display all address records.
Possible values: ALL, ADNS, PROXY



##Outputs

<b>nextNsec</b>
Next nsec record in the chain

<b>nsecBitarray</b>
Bit array representing the different record types configured for the domain name

<b>nextRecs</b>
An array of record types associated with the nsec record.

<b>TTL</b>
Time to Live (TTL), in seconds, for the record.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show dns nsecRec foo.bar

