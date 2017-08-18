#filter prebodyInjection

The following operations can be performed on "filter prebodyInjection":


[set](#set-filter-prebodyinjection) | [unset](#unset-filter-prebodyinjection) | [show](#show-filter-prebodyinjection)

##set filter prebodyInjection

Specifies the file to be used for prebody injection. NOTE: This command is deprecated.Deprecated in favour of Client Side Measurements that can be enabled on an appflow action


##Synopsys




##Arguments

<b>prebody</b>
Name of file whose contents are to be inserted before the response body.



##Example

set filter prebodyInjection ens/prebody.js

##unset filter prebodyInjection

Removes the setting that specifies the file used for prebody injection..Refer to the set filter prebodyInjection command for meanings of the arguments.NOTE: This command is deprecated.Deprecated in favour of Client Side Measurements that can be enabled on an appflow action


##Synopsys




##Example

unset filter prebodyInjection

##show filter prebodyInjection

Displays the name of the file used for prebody injection. NOTE: This command is deprecated.Deprecated in favour of Client Side Measurements that can be enabled on an appflow action


##Synopsys




##Outputs

<b>prebody</b>
The name of the prebody file.

<b>systemIID</b>
The system IID of the current NetScaler system.



