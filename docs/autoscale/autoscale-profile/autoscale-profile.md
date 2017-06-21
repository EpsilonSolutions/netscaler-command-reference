#autoscale profile

The following operations can be performed on "autoscale profile":


[add](#add-autoscale-profile) | [rm](#rm-autoscale-profile) | [set](#set-autoscale-profile) | [show](#show-autoscale-profile)

##add autoscale profile

Create a AutoScale policy.


##Synopsys

add autoscale profile &lt;name> -type CLOUDSTACK -url &lt;URL> -apiKey  -sharedSecret 


##Arguments

<b>name</b>
AutoScale profile name.

<b>type</b>
The type of profile.
Possible values: CLOUDSTACK

<b>url</b>
URL providing the service

<b>apiKey</b>
api key for authentication with service

<b>sharedSecret</b>
shared secret for authentication with service



##rm autoscale profile

Remove a AutoScale policy.


##Synopsys

rm autoscale profile &lt;name>


##Arguments

<b>name</b>
AutoScale profile name.



##set autoscale profile

Set a AutoScale policy.


##Synopsys

set autoscale profile &lt;name> [-url &lt;URL>] [-apiKey ] [-sharedSecret ]


##Arguments

<b>name</b>
AutoScale profile name.

<b>url</b>
URL providing the service

<b>apiKey</b>
api key for authentication with service

<b>sharedSecret</b>
shared secret for authentication with service



##show autoscale profile

Display the autoscale profile.


##Synopsys

show autoscale profile [&lt;name>]


##Arguments

<b>name</b>
AutoScale profile name.



##Outputs

<b>type</b>
The type of profile.

<b>url</b>
URL providing the service

<b>apiKey</b>
api key for authentication with service

<b>sharedSecret</b>
shared secret for authentication with service

<b>stateflag</b>

<b>devno</b>

<b>count</b>



