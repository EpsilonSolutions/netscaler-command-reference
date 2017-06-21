#filter prebodyInjection

The following operations can be performed on "filter prebodyInjection":


[set](#set-filter-prebodyinjection) | [unset](#unset-filter-prebodyinjection) | [show](#show-filter-prebodyinjection)

##set filter prebodyInjection

Specifies the file to be used for prebody injection.


##Synopsys

set filter prebodyInjection &lt;prebody>


##Arguments

<b>prebody</b>
Name of file whose contents are to be inserted before the response body.



##Example

set filter prebodyInjection ens/prebody.js

##unset filter prebodyInjection

Removes the setting that specifies the file used for prebody injection..Refer to the set filter prebodyInjection command for meanings of the arguments.


##Synopsys

unset filter prebodyInjection [-prebody]


##Example

unset filter prebodyInjection

##show filter prebodyInjection

Displays the name of the file used for prebody injection.


##Synopsys

show filter prebodyInjection


##Outputs

<b>prebody</b>
The name of the prebody file.

<b>systemIID</b>
The system IID of the current NetScaler system.



