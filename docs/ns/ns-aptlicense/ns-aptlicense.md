#ns aptlicense

The following operations can be performed on "ns aptlicense":


[show](#show-ns-aptlicense) | [update](#update-ns-aptlicense)

##show ns aptlicense




##Synopsys

show ns aptlicense &lt;serialNo> [-useProxy ( YES | NO )]


##Arguments

<b>serialNo</b>
Hardware Serial Number/License Activation Code(LAC)

<b>useProxy</b>
Specifies whether to use the licenseproxyserver to reach the internet. Make sure to configure licenseproxyserver to use this option.
Possible values: YES, NO
Default value: NO



##Outputs

<b>response</b>
Response data as text blob

<b>id</b>
License ID

<b>sessionId</b>
Session ID

<b>bindType</b>
Bind type

<b>countAvailable</b>
Count

<b>countTotal</b>
Count

<b>name</b>
License name

<b>relevance</b>
License relevance

<b>datePurchased</b>
License purchase date

<b>dateSa</b>
License SA date

<b>dateExp</b>
License expiry date

<b>features</b>
Features



##Example

show ns aptlicense &lt;hw-no/lac&gt;

##update ns aptlicense




##Synopsys

update ns aptlicense &lt;id> &lt;sessionId> &lt;bindType> &lt;countAvailable> [&lt;licenseDir>] [-useProxy ( YES | NO )]


##Arguments

<b>id</b>
License ID

<b>sessionId</b>
Session ID

<b>bindType</b>
Bind type

<b>countAvailable</b>
The user can allocate one or more licenses. Ensure the value is less than (for partial allocation) or equal to the total number of available licenses

<b>licenseDir</b>
License Directory

<b>useProxy</b>
Specifies whether to use the licenseproxyserver to reach the internet. Make sure to configure licenseproxyserver to use this option.
Possible values: YES, NO
Default value: NO



##Example

update ns aptlicense key1 sessionID#  HOSTNAME 1

