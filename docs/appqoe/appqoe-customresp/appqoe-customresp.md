#appqoe CustomResp

The following operations can be performed on "appqoe CustomResp":


[import](#import-appqoe-customresp) | [rm](#rm-appqoe-customresp) | [show](#show-appqoe-customresp) | [update](#update-appqoe-customresp)

##import appqoe CustomResp

Downloads the input HTML Page to NetScaler Box with the given object name


##Synopsys

import appqoe CustomResp [&lt;src>] &lt;name>


##Arguments

<b>src</b>

<b>name</b>
Indicates name of the custom response HTML page to import/update.



##Example

import appqoe CustomResp http://10.102.34.25/index.html appqoe_resp

##rm appqoe CustomResp

Removes the imported HTML object.


##Synopsys

rm appqoe CustomResp &lt;name>


##Arguments

<b>name</b>
Indicates name of the custom response HTML page to import/update.



##Example

rm appqoe CustomResp appqoe_resp

##show appqoe CustomResp

Displays lists all HTML page objects on the NetScaler appliance.


##Synopsys

show appqoe CustomResp


##Outputs

<b>name</b>
Indicates name of the custom response HTML page to import/update.

<b>src</b>

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show appqoe CustomResp

##update appqoe CustomResp

Update the imported HTML object


##Synopsys

update appqoe CustomResp &lt;name>


##Arguments

<b>name</b>
Indicates name of the custom response HTML page to import/update.



##Example

update appqoe CustomResp appqoe_resp

