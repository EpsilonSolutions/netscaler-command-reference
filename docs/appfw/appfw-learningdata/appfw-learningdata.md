#appfw learningdata

The following operations can be performed on "appfw learningdata":


[rm](#rm-appfw-learningdata) | [show](#show-appfw-learningdata) | [reset](#reset-appfw-learningdata) | [export](#export-appfw-learningdata)

##rm appfw learningdata

Removes unreviewed application firewall learning data for the specified application firewall profile.


##Synopsys

rm appfw learningdata &lt;profileName> (-startURL &lt;expression> | -cookieConsistency &lt;string> | (-fieldConsistency &lt;string>  &lt;formActionURL>) | (-crossSiteScripting &lt;string>  &lt;formActionURL>  [&lt;location>]) | (-SQLInjection &lt;string>  &lt;formActionURL>  [&lt;location>]) | (-fieldFormat &lt;string>  &lt;formActionURL>) | (-CSRFTag &lt;expression>  &lt;CSRFFormOriginURL>) | -XMLDoSCheck &lt;expression> | -XMLWSICheck &lt;expression> | -XMLAttachmentCheck &lt;expression>) [-TotalXMLRequests]


##Arguments

<b>profileName</b>
Name of the profile.

<b>startURL</b>
Start URL configuration.

<b>cookieConsistency</b>
Cookie Name.

<b>fieldConsistency</b>
Form field name.

<b>crossSiteScripting</b>
Cross-site scripting.

<b>SQLInjection</b>
Form field name.

<b>fieldFormat</b>
Field format name.

<b>CSRFTag</b>
CSRF Form Action URL

<b>XMLDoSCheck</b>
XML Denial of Service check, one of
	MaxAttributes
	MaxAttributeNameLength
	MaxAttributeValueLength
	MaxElementNameLength
	MaxFileSize
	MinFileSize
	MaxCDATALength
	MaxElements
	MaxElementDepth
	MaxElementChildren
	NumDTDs
	NumProcessingInstructions
	NumExternalEntities
	MaxEntityExpansions
	MaxEntityExpansionDepth
	MaxNamespaces
	MaxNamespaceUriLength
	MaxSOAPArraySize
	MaxSOAPArrayRank

<b>XMLWSICheck</b>
Web Services Interoperability Rule ID.

<b>XMLAttachmentCheck</b>
XML Attachment Content-Type.

<b>TotalXMLRequests</b>
Total XML requests.



##show appfw learningdata

Displays the unreviewed application firewall learning data for the specified profile and security check.


##Synopsys

show appfw learningdata &lt;profileName> &lt;securityCheck>


##Arguments

<b>profileName</b>
Name of the profile.

<b>securityCheck</b>
Name of the security check.
Possible values: startURL, cookieConsistency, fieldConsistency, crossSiteScripting, SQLInjection, fieldFormat, CSRFtag, XMLDoSCheck, XMLWSICheck, XMLAttachmentCheck, TotalXMLRequests

<b>summary</b>

<b>fullValues</b>



##Outputs

<b>data</b>
Learned data.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##reset appfw learningdata

Remove all databases. Make transaction count zero


##Synopsys

reset appfw learningdata


##export appfw learningdata

Export appfw learnt data in csv format to the location /var/learnt_data/


##Synopsys

export appfw learningdata &lt;profileName> &lt;securityCheck> [-target &lt;string>]


##Arguments

<b>profileName</b>
Name of the profile.

<b>securityCheck</b>
Name of the security check.
Possible values: startURL, cookieConsistency, fieldConsistency, crossSiteScripting, SQLInjection, fieldFormat, CSRFtag, XMLDoSCheck, XMLWSICheck, XMLAttachmentCheck, TotalXMLRequests

<b>target</b>
Target filename for data to be exported.



