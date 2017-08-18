#ns servicePath

The following operations can be performed on "ns servicePath":


[add](#add-ns-servicepath) | [rm](#rm-ns-servicepath) | [bind](#bind-ns-servicepath) | [unbind](#unbind-ns-servicepath) | [show](#show-ns-servicepath)

##add ns servicePath

Creates a Servicepath.


##Synopsys

add ns servicePath &lt;servicePathName>


##Arguments

<b>servicePathName</b>
Name for the Service path. Must begin with an ASCII alphanumeric or underscore (_) character, and must
      contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-)
      characters.



##Example

add servicepath SP1

##rm ns servicePath

Removes a ServicePath.


##Synopsys

rm ns servicePath &lt;servicePathName>


##Arguments

<b>servicePathName</b>
Name for the Service path. Must begin with an ASCII alphanumeric or underscore (_) character, and must
      contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-)
      characters.



##Example

rm servicepath SP1

##bind ns servicePath

Bind service functions to path to define the path.


##Synopsys

bind ns servicePath &lt;servicePathName> -serviceFunction &lt;string> -index &lt;positive_integer>


##Arguments

<b>servicePathName</b>
Name for the Service path. Must begin with an ASCII alphanumeric or underscore (_) character, and must
      contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-)
      characters.

<b>serviceFunction</b>
Name of the service function to bind to path.

<b>index</b>
Integer to specify the order, lower the number denotes further down in service chain.
Minimum value: 1



##Example

bind servicepath SP1 -servicefunction SF1 -index 255

##unbind ns servicePath

unbind servicefunctions from servicepath.


##Synopsys

unbind ns servicePath &lt;servicePathName> -serviceFunction &lt;string>


##Arguments

<b>servicePathName</b>
Name for the Service path. Must begin with an ASCII alphanumeric or underscore (_) character, and must
      contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-)
      characters.

<b>serviceFunction</b>
Name of the ServiceFunction to bind to ServicePath.



##Example

unbind servicepath SP1 -servicefunction SF1

##show ns servicePath

Displays ServicePath.


##Synopsys

show ns servicePath [&lt;servicePathName>]


##Arguments

<b>servicePathName</b>
Name for the Service path. Must begin with an ASCII alphanumeric or underscore (_) character, and must
      contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-)
      characters.



##Outputs

<b>serviceFunction</b>
List of service functions constituting the chain.

<b>index</b>
The serviceindex of each servicefunction in path.

<b>stateflag</b>
the field for stateflags.

<b>devno</b>

<b>count</b>



##Example

show servicepath SC1

