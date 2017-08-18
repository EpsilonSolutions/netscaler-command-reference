#locationParameter

The following operations can be performed on "locationParameter":


[set](#set-locationparameter) | [unset](#unset-locationparameter) | [show](#show-locationparameter)

##set locationParameter

Sets the location parameters used for static-proximity based global server load balancing. Location parameters include up to six qualifiers and a context that specifies how the qualifiers must be interpreted. Each qualifier specifies the location of an IP address range and is more specific than the one that precedes it, as in continent.country.region.city.isp.organization. For example, "NA.US.CA.San Jose.ATT.citrix". Note: A qualifier that includes a dot (.) or space ( ) must be enclosed in double quotation marks.


##Synopsys

set locationParameter [-context ( geographic | custom )] [-q1label &lt;string>] [-q2label &lt;string>] [-q3label &lt;string>] [-q4label &lt;string>] [-q5label &lt;string>] [-q6label &lt;string>]


##Arguments

<b>context</b>
Context for describing locations. In geographic context, qualifier labels are assigned by default in the following sequence: Continent.Country.Region.City.ISP.Organization. In custom context, the qualifiers labels can have any meaning that you designate.
Possible values: geographic, custom

<b>q1label</b>
Label specifying the meaning of the first qualifier. Can be specified for custom context only.

<b>q2label</b>
Label specifying the meaning of the second qualifier. Can be specified for custom context only.

<b>q3label</b>
Label specifying the meaning of the third qualifier. Can be specified for custom context only.

<b>q4label</b>
Label specifying the meaning of the fourth qualifier. Can be specified for custom context only.

<b>q5label</b>
Label specifying the meaning of the fifth qualifier. Can be specified for custom context only.

<b>q6label</b>
Label specifying the meaning of the sixth qualifier. Can be specified for custom context only.



##Example

set locationparameter -context   custom

##unset locationParameter

Use this command to remove  locationParameter settings.Refer to the set  locationParameter command for meanings of the arguments.


##Synopsys

unset locationParameter [-context] [-q1label] [-q2label] [-q3label] [-q4label] [-q5label] [-q6label]


##show locationParameter

Displays current values for the location parameters, which are used for static-proximity based load balancing.


##Synopsys

show locationParameter


##Outputs

<b>context</b>
The context in which a static proximity decision must be made.

<b>q1label</b>
The label for the 1st qualifier. These qualifier labels characterize the locations mapped with the IP addresses used to make static proximity decisions.

<b>q2label</b>
Label specifying the meaning of the second qualifier. Can be specified for custom context only.

<b>q3label</b>
Label specifying the meaning of the third qualifier. Can be specified for custom context only.

<b>q4label</b>
Label specifying the meaning of the fourth qualifier. Can be specified for custom context only.

<b>q5label</b>
Label specifying the meaning of the fifth qualifier. Can be specified for custom context only.

<b>q6label</b>
Label specifying the meaning of the sixth qualifier. Can be specified for custom context only.

<b>locationFile</b>
Currently loaded location database file.

<b>format</b>
Location file format

<b>custom</b>
Number of configured custom locations.

<b>static</b>
Number of configured locations in the database file (static locations).

<b>lines</b>
Number of lines in the databse files

<b>errors</b>
Number of errros encountered while reading the database file.

<b>warnings</b>
Number of warnings encountered while reading the database file.

<b>entries</b>
Number of successfully added entries.

<b>locationFile6</b>
Currently loaded location database file.

<b>format6</b>
Location file format

<b>custom6</b>
Number of configured custom locations.

<b>static6</b>
Number of configured locations in the database file (static locations).

<b>lines6</b>
Number of lines in the databse files

<b>errors6</b>
Number of errros encountered while reading the database file.

<b>warnings6</b>
Number of warnings encountered while reading the database file.

<b>entries6</b>
Number of successfully added entries.

<b>flags</b>
Information needed for display. This argument passes information from the kernel to the user space.

<b>status</b>
This argument displays when the status (success or failure) of database loading.

<b>DatabaseMode</b>
This argument displays the database mode.

<b>flushing</b>
This argument displays the state of flushing.

<b>loading</b>
This argument displays the state of loading.

<b>matchWildcardtoany</b>
Indicates whether wildcard qualifiers should match any other qualifier including non-wildcard. Option to fallback after default behavior changes to not match



##Example

show locationparameter

