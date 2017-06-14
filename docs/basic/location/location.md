#location

The following operations can be performed on "location":


[add](#add-location) | [rm](#rm-location) | [show](#show-location)

##add location

Creates a custom location entry on the NetScaler appliance. Custom locations can be used instead of a static location database if the number of locations you need does not exceed 500. Custom locations can also be used to override incorrect entries in the static database, because the appliance searches the static database before it searches the static location database.


##Synopsys

add location &lt;IPfrom> &lt;IPto> &lt;preferredLocation> [-longitude &lt;integer>  [-latitude &lt;integer>]]


##Arguments

<b>IPfrom</b>
First IP address in the range, in dotted decimal notation.

<b>IPto</b>
Last IP address in the range, in dotted decimal notation.

<b>preferredLocation</b>
String of qualifiers, in dotted notation, describing the geographical location of the IP address range. Each qualifier is more specific than the one that precedes it, as in continent.country.region.city.isp.organization. For example, "NA.US.CA.San Jose.ATT.citrix". 
Note: A qualifier that includes a dot (.) or space ( ) must be enclosed in double quotation marks.

<b>longitude</b>
Numerical value, in degrees, specifying the longitude of the geographical location of the IP address-range. 
Note: Longitude and latitude parameters are used for selecting a service with the static proximity GSLB method. If they are not specified, selection is based on the qualifiers specified for the location.
Minimum value: -180
Maximum value: 180

<b>latitude</b>
Numerical value, in degrees, specifying the latitude of the geographical location of the IP address-range. 
Note: Longitude and latitude parameters are used for selecting a service with the static proximity GSLB method. If they are not specified, selection is based on the qualifiers specified for the location.
Minimum value: -90
Maximum value: 90



##Example

Add location 192.168.100.1 192.168.100.100 *.us.ca.san jose

##rm location

Removes a custom location entry from the NetScaler appliance.


##Synopsys

rm location &lt;IPfrom> &lt;IPto>


##Arguments

<b>IPfrom</b>
First IP address in the range, in dotted decimal notation.

<b>IPto</b>
Last IP address in the range, in dotted decimal notation.



##Example

rm location 192.168.100.1 192.168.100.100

##show location

Displays all the custom location entries configured on the NetScaler appliance, or just the entry for the specified IP address range.


##Synopsys

show location [&lt;IPfrom>]


##Arguments

<b>IPfrom</b>
The qualifiers in dotted notation for the ipaddress. If this value is not specified, all custom entries are displayed.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>IPto</b>
The end of the IP address range.

<b>preferredLocation</b>
The qualifiers in dotted notation for the ipaddress range.

<b>q1label</b>
Least specific location qualifier.

<b>q2label</b>
Location qualifier 2.

<b>q3label</b>
Location qualifier 3.

<b>q4label</b>
Location qualifier 4.

<b>q5label</b>
Location qualifier 5.

<b>q6label</b>
Most specific location qualifier.

<b>longitude</b>
Numerical value, in degrees, specifying the longitude of the geographical location of the IP address-range. 
Note: Longitude and latitude parameters are used for selecting a service with the static proximity GSLB method. If they are not specified, selection is based on the qualifiers specified for the location.

<b>latitude</b>
Numerical value, in degrees, specifying the latitude of the geographical location of the IP address-range. 
Note: Longitude and latitude parameters are used for selecting a service with the static proximity GSLB method. If they are not specified, selection is based on the qualifiers specified for the location.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show location

