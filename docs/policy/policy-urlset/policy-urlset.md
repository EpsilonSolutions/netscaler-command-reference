#policy urlset

The following operations can be performed on "policy urlset":


[add](#add-policy-urlset) | [rm](#rm-policy-urlset) | [show](#show-policy-urlset) | [import](#import-policy-urlset) | [update](#update-policy-urlset) | [export](#export-policy-urlset)

##add policy urlset

Adds a url set.


##Synopsys

add policy urlset &lt;name> [-comment &lt;string>]


##Arguments

<b>name</b>
Unique name of the url set. Not case sensitive. Must begin with an ASCII letter or underscore (_) character and must contain only alphanumeric and underscore characters. Must not be the name of an existing named expression, pattern set, dataset, string map, or HTTP callout.

<b>comment</b>
Any comments to preserve information about this url set.



##Example

add policy urlset urlset1

##rm policy urlset

Removes a url set. If the url set is used by an expression in another object, such as a policy, you must remove the object before removing the url set.


##Synopsys

rm policy urlset &lt;name>


##Arguments

<b>name</b>
Name of the url set to remove.



##Example

rm urlset urlset1

##show policy urlset

Displays information about the configured urlsets.


##Synopsys

show policy urlset [&lt;name>]


##Arguments

<b>name</b>
Name of the url set for which to display the detailed information. If a name is not provided, a list of all url sets configured on the appliance is shown.



##Outputs

<b>comment</b>
Any comments to preserve information about this url set.

<b>patternCount</b>
Number of patterns in this urlset.

<b>url</b>
URL (protocol, host, path and file name) from where the CSV (comma separated file) file will be imported or exported. Each record/line will one entry within the urlset. The first field contains the URL pattern, subsequent fields contains the metadata, if available. HTTP, HTTPS and FTP protocols are supported. NOTE: The operation fails if the destination HTTPS server requires client certificate authentication for access.

<b>delimiter</b>
CSV file record delimiter.

<b>rowSeparator</b>
CSV file row separator.

<b>interval</b>
The interval, in seconds, rounded down to the nearest 15 minutes, at which the update of urlset occurs.

<b>canaryUrl</b>
Add this URL to this urlset. Used for testing when contents of urlset is kept confidential.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show policy urlset urlset1

##import policy urlset

Imports the specified urlset to the NetScaler appliance, assigns it the specified name.


##Synopsys

import policy urlset &lt;name> [-overwrite] [-delimiter &lt;character>] [-rowSeparator &lt;character>] -url &lt;URL> [-interval &lt;secs>] [-privateSet] [-canaryUrl &lt;URL>]


##Arguments

<b>name</b>
Unique name of the url set. Not case sensitive. Must begin with an ASCII letter or underscore (_) character and must contain only alphanumeric and underscore characters. Must not be the name of an existing named expression, pattern set, dataset, string map, or HTTP callout.

<b>overwrite</b>
Overwrites the existing file.
Default value: 0

<b>delimiter</b>
CSV file record delimiter.
Default value: 44

<b>rowSeparator</b>
CSV file row separator.
Default value: 10

<b>url</b>
URL (protocol, host, path and file name) from where the CSV (comma separated file) file will be imported or exported. Each record/line will one entry within the urlset. The first field contains the URL pattern, subsequent fields contains the metadata, if available. HTTP, HTTPS and FTP protocols are supported. NOTE: The operation fails if the destination HTTPS server requires client certificate authentication for access.

<b>interval</b>
The interval, in seconds, rounded down to the nearest 15 minutes, at which the update of urlset occurs.
Default value: 0
Maximum value: 2592000

<b>privateSet</b>
Prevent this urlset from being exported.
Default value: 0

<b>canaryUrl</b>
Add this URL to this urlset. Used for testing when contents of urlset is kept confidential.



##Example

import policy urlset urlset1 -url http://www.example.com/file_1

##update policy urlset

Update the specified urlset from the source.


##Synopsys

update policy urlset &lt;name>


##Arguments

<b>name</b>
Name of the urlset to update.



##Example

update policy urlset urlset1

##export policy urlset

Exports the specified urlset to the URL. Ensure the URL accepts a PUT request for HTTP/HTTPS URL.


##Synopsys

export policy urlset &lt;name> -url &lt;URL>


##Arguments

<b>name</b>
Unique name of the url set. Not case sensitive. Must begin with an ASCII letter or underscore (_) character and must contain only alphanumeric and underscore characters. Must not be the name of an existing named expression, pattern set, dataset, string map, or HTTP callout.

<b>url</b>
URL (protocol, host, path and file name) from where the CSV (comma separated file) file will be imported or exported. Each record/line will one entry within the urlset. The first field contains the URL pattern, subsequent fields contains the metadata, if available. HTTP, HTTPS and FTP protocols are supported. NOTE: The operation fails if the destination HTTPS server requires client certificate authentication for access.



##Example

export policy urlset urlset1 -url http://www.example.com/PUT_file_1

