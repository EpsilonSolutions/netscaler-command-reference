#system collectionparam

The following operations can be performed on "system collectionparam":


[set](#set-system-collectionparam) | [unset](#unset-system-collectionparam) | [show](#show-system-collectionparam)

##set system collectionparam

Modifies a collection parameters for historical charting in nscollect.ini file.


##Synopsys

set system collectionparam [-logLevel &lt;string>] [-dataPath &lt;string>]


##Arguments

<b>logLevel</b>
specify the log level. Possible values CRITICAL,WARNING,INFO,DEBUG1,DEBUG2

<b>dataPath</b>
specify the data path to the database.



##unset system collectionparam

Use this command to remove system collectionparam settings.Refer to the set system collectionparam command for meanings of the arguments.


##Synopsys

unset system collectionparam [-logLevel] [-dataPath]


##show system collectionparam

Displays collection parameters for historical charting present in nscollect.ini file.


##Synopsys

show system collectionparam


##Outputs

<b>communityName</b>
SNMPv1 community name for authentication.

<b>logLevel</b>
specify the log level. Possible values CRITICAL,WARNING,INFO,DEBUG1,DEBUG2

<b>dataPath</b>
specify the data path to the database.



