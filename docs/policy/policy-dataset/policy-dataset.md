#policy dataset

The following operations can be performed on "policy dataset":


[add](#add-policy-dataset) | [rm](#rm-policy-dataset) | [bind](#bind-policy-dataset) | [unbind](#unbind-policy-dataset) | [show](#show-policy-dataset)

##add policy dataset

Adds a policy dataset to the appliance.


##Synopsys

add policy dataset &lt;name> &lt;type> [-comment &lt;string>]


##Arguments

<b>name</b>
Name of the dataset. Must not exceed 127 characters.

<b>type</b>
Type of value to bind to the dataset.
Possible values: ipv4, number, ipv6, ulong, double, mac

<b>comment</b>
Any comments to preserve information about this dataset.



##Example

add policy dataset ts1 -type IPV4

##rm policy dataset

Removes a dataset from the appliance.


##Synopsys

rm policy dataset &lt;name>


##Arguments

<b>name</b>
Name of the dataset to remove.



##Example

rm policy dataset pat1

##bind policy dataset

Binds a value of the specified type to the dataset. If the first value is bound by using an index label, the other bind statements to that set should also provide an index.


##Synopsys

bind policy dataset &lt;name> &lt;value> [-index &lt;positive_integer>]


##Arguments

<b>name</b>
Name of the dataset to which to bind the value.

<b>value</b>
Value of the specified type that is associated with the dataset.

<b>index</b>
The Index of the value associated with set.
Minimum value: 1
Maximum value: 4294967290



##Example

bind policy dataset ts1 192.168.20.1 -index 2

##unbind policy dataset

Unbind string(s) from a dataset.


##Synopsys

unbind policy dataset &lt;name> &lt;value>


##Arguments

<b>name</b>
Name of the dataset from which to unbind the value.

<b>value</b>
Value to unbind from the dataset.



##Example

unbind policy dataset pat1 bar xyz

##show policy dataset

Display the configured dataset(s).


##Synopsys

show policy dataset [&lt;name>]


##Arguments

<b>name</b>
Name of the dataset. Must not exceed 127 characters.



##Outputs

<b>stateflag</b>

<b>value</b>
Value of the specified type that is associated with the dataset.

<b>index</b>
The index of the value (ipv4, ipv6, number) associated with the set.

<b>description</b>
Description of the set

<b>type</b>
Type of value to bind to the dataset.

<b>indexType</b>
Index type.

<b>MaxIndex</b>
Maximum number of values bounded to dataset. The maxindex value will not be decreased when we unbind a value from the dataset. This field is used in auto-generated indexing type.

<b>comment</b>
Any comments to preserve information about this dataset.

<b>devno</b>

<b>count</b>



##Example

show policy dataset set1

