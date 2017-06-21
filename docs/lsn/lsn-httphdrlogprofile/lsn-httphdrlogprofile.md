#lsn httphdrlogprofile

The following operations can be performed on "lsn httphdrlogprofile":


[add](#add-lsn-httphdrlogprofile) | [rm](#rm-lsn-httphdrlogprofile) | [set](#set-lsn-httphdrlogprofile) | [unset](#unset-lsn-httphdrlogprofile) | [show](#show-lsn-httphdrlogprofile)

##add lsn httphdrlogprofile

Add LSN HTTP header logging Profile.


##Synopsys

add lsn httphdrlogprofile &lt;httphdrlogprofilename> [-logURL ( ENABLED | DISABLED )] [-logMethod ( ENABLED | DISABLED )] [-logVersion ( ENABLED | DISABLED )] [-logHost ( ENABLED | DISABLED )]


##Arguments

<b>httphdrlogprofilename</b>
The name of the HTTP header logging Profile.

<b>logURL</b>
URL information is looged if option is enabled.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>logMethod</b>
HTTP method information is looged if option is enabled.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>logVersion</b>
Version information is looged if option is enabled.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>logHost</b>
Host information is looged if option is enabled.
Possible values: ENABLED, DISABLED
Default value: ENABLED



##Example

add lsn httphdrlogprofile profile1  -url ENABLED

##rm lsn httphdrlogprofile

Remove LSN HTTP header logging Profile.


##Synopsys

rm lsn httphdrlogprofile &lt;httphdrlogprofilename>


##Arguments

<b>httphdrlogprofilename</b>
The name of the HTTP header logging Profile.



##Example

rm lsn transportprofile profile1 

##set lsn httphdrlogprofile

Set  LSN HTTP header logging Profile.


##Synopsys

set lsn httphdrlogprofile &lt;httphdrlogprofilename> [-logURL ( ENABLED | DISABLED )] [-logMethod ( ENABLED | DISABLED )] [-logVersion ( ENABLED | DISABLED )] [-logHost ( ENABLED | DISABLED )]


##Arguments

<b>httphdrlogprofilename</b>
The name of the HTTP header logging Profile.

<b>logURL</b>
URL information is looged if option is enabled.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>logMethod</b>
HTTP method information is looged if option is enabled.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>logVersion</b>
Version information is looged if option is enabled.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>logHost</b>
Host information is looged if option is enabled.
Possible values: ENABLED, DISABLED
Default value: ENABLED



##Example

set lsn transportprofile profile1 -portquota 128

##unset lsn httphdrlogprofile

Use this command to remove lsn httphdrlogprofile settings.Refer to the set lsn httphdrlogprofile command for meanings of the arguments.


##Synopsys

unset lsn httphdrlogprofile &lt;httphdrlogprofilename> [-logURL] [-logMethod] [-logVersion] [-logHost]


##show lsn httphdrlogprofile

Display LSN HTTP header logging Profile.


##Synopsys

show lsn httphdrlogprofile [&lt;httphdrlogprofilename>]


##Arguments

<b>httphdrlogprofilename</b>
The name of the HTTP header logging Profile.



##Outputs

<b>logURL</b>
URL information is looged if option is enabled.

<b>logMethod</b>
HTTP method information is looged if option is enabled.

<b>logVersion</b>
Version information is looged if option is enabled.

<b>logHost</b>
Host information is looged if option is enabled.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show lsn transportprofile profile1

