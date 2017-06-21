#locationFile

The following operations can be performed on "locationFile":


[add](#add-locationfile) | [rm](#rm-locationfile) | [show](#show-locationfile)

##add locationFile

Loads the static location database from the specified file.


##Synopsys

add locationFile &lt;locationFile> [-format &lt;format>]


##Arguments

<b>locationFile</b>
Name of the location file, with or without absolute path. If the path is not included, the default path (/var/netscaler/locdb) is assumed. In a high availability setup, the static database must be stored in the same location on both NetScaler appliances.

<b>format</b>
Format of the location file. Required for the NetScaler appliance to identify how to read the location file.
Possible values: netscaler, ip-country, ip-country-isp, ip-country-region-city, ip-country-region-city-isp, geoip-country, geoip-region, geoip-city, geoip-country-org, geoip-country-isp, geoip-city-isp-org
Default value: netscaler



##Example

add locationfile /var/nsmap/locationdb  -format netscaler

##rm locationFile

Removes the currently loaded static location database from the NetScaler appliance.


##Synopsys

rm locationFile


##Example

rm locationfile

##show locationFile

Displays the name, including the absolute path, and format of the location file currently loaded on the NetScaler appliance.


##Synopsys

show locationFile


##Outputs

<b>locationFile</b>
The name of the location file.

<b>format</b>
The format of the location file.



##Example

show locationfile

