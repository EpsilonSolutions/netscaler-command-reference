#ns xmlnamespace

The following operations can be performed on "ns xmlnamespace":


[add](#add-ns-xmlnamespace) | [rm](#rm-ns-xmlnamespace) | [set](#set-ns-xmlnamespace) | [unset](#unset-ns-xmlnamespace) | [show](#show-ns-xmlnamespace)

##add ns xmlnamespace

Adds a mapping between an XML prefix and a namespace URI (Uniform Resource Identifier).


##Synopsys

add ns xmlnamespace &lt;prefix> &lt;namespace> [-description &lt;string>]


##Arguments

<b>prefix</b>
XML prefix.

<b>namespace</b>
Expanded namespace for which the XML prefix is provided.

<b>description</b>
Description for the prefix.



##Example

add ns xmlnamespace soap http://schemas.xmlsoap.org/soap/envelope/

##rm ns xmlnamespace

Removes the mapping between an XML prefix and a namespace URI.


##Synopsys

rm ns xmlnamespace &lt;prefix>


##Arguments

<b>prefix</b>
XML prefix for which the mapping must be removed.



##Example

rm ns xmlnamespace soap

##set ns xmlnamespace

Modifies the mapping between an XML prefix and a namespace URI.


##Synopsys

set ns xmlnamespace &lt;prefix> [&lt;namespace>] [-description &lt;string>]


##Arguments

<b>prefix</b>
XML prefix for which the namespace or description must be added or updated.

<b>namespace</b>
Expanded namespace for which the XML prefix is provided.

<b>description</b>
Description for the prefix.



##Example

set ns xmlnamespace soap -description SOAP/1.1

##unset ns xmlnamespace

Use this command to remove ns xmlnamespace settings.Refer to the set ns xmlnamespace command for meanings of the arguments.


##Synopsys

unset ns xmlnamespace &lt;prefix> [-namespace] [-description]


##show ns xmlnamespace

Displays the mappings between XML prefixes to namespace URIs.


##Synopsys

show ns xmlnamespace [&lt;prefix>]


##Arguments

<b>prefix</b>
Name of the prefix for which the mappings must be displayed.



##Outputs

<b>namespace</b>
Expanded namespace for which the XML prefix is provided.

<b>description</b>
Description for the prefix.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show ns xmlnamespace soap

