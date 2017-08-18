#filter postbodyInjection

The following operations can be performed on "filter postbodyInjection":


[set](#set-filter-postbodyinjection) | [unset](#unset-filter-postbodyinjection) | [show](#show-filter-postbodyinjection)

##set filter postbodyInjection

Specifies the file to be used for postbody injection. NOTE: This command is deprecated.Deprecated in favour of Client Side Measurements that can be enabled on an appflow action


##Synopsys




##Arguments

<b>postbody</b>
Name of file whose contents are to be inserted after the response body.



##Example

set filter postbodyInjection ens/postbody.js

##unset filter postbodyInjection

Removes the setting that specifies the file used for postbody injection..Refer to the set filter postbodyInjection command for meanings of the arguments.NOTE: This command is deprecated.Deprecated in favour of Client Side Measurements that can be enabled on an appflow action


##Synopsys




##Example

unset filter postbodyInjection

##show filter postbodyInjection

Displays the name of the file used for postbody injection. NOTE: This command is deprecated.Deprecated in favour of Client Side Measurements that can be enabled on an appflow action


##Synopsys




##Outputs

<b>postbody</b>
The name of the postbody file.

<b>systemIID</b>
The system IID of the current NetScaler system.



