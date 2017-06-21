#appfw learningdata

The following operations can be performed on "appfw learningdata":


[rm](#rm-appfw-learningdata) | [show](#show-appfw-learningdata) | [reset](#reset-appfw-learningdata) | [export](#export-appfw-learningdata)

##rm appfw learningdata

Removes unreviewed application firewall learning data for the specified application firewall profile.


##Synopsys

rm appfw learningdata &lt;profileName> (-startURL &lt;expression> | -cookieConsistency &lt;string> | (-fieldConsistency &lt;string>  &lt;formActionURL>) | -contentType &lt;string> | (-crossSiteScripting &lt;string>  &lt;formActionURL>  [&lt;location>]  [&lt;valueType>  &lt;valueExpression>]) | (-SQLInjection &lt;string>  &lt;formActionURL>  [&lt;location>]  [&lt;valueType>  &lt;valueExpression>]) | (-fieldFormat &lt;string>  &lt;formActionURL>) | (-CSRFTag &lt;expression>  &lt;CSRFFormOriginURL>) | (-CreditCardNumber &lt;expression>  &lt;CreditCardNumberUrl>) | -XMLDoSCheck &lt;expression> | -XMLWSICheck &lt;expression> | -XMLAttachmentCheck &lt;expression>) [-TotalXMLRequests]


##Arguments

<b>profileName</b>
Name of the profile.

<b>startURL</b>
Start URL configuration.

<b>cookieConsistency</b>
Cookie Name.

<b>fieldConsistency</b>
Form field name.

<b>formActionURL</b>
Form action URL.

<b>contentType</b>
Content Type Name.

<b>crossSiteScripting</b>
Cross-site scripting.

<b>location</b>
Location of sql injection exception - form field, header or cookie.
Possible values: FORMFIELD, HEADER, COOKIE

<b>valueType</b>
SQL value type. Keyword, SpecialString or Wildchar
Possible values: Keyword, SpecialString, Wildchar

<b>valueExpression</b>
SQL value expressions consistituting expressions for Keyword, SpecialString or Wildchar.

<b>SQLInjection</b>
Form field name.

<b>fieldFormat</b>
Field format name.

<b>CSRFTag</b>
CSRF Form Action URL

<b>CSRFFormOriginURL</b>
CSRF Form Origin URL.

<b>CreditCardNumber</b>
The object expression that is to be excluded from safe commerce check.

<b>CreditCardNumberUrl</b>
The url for which the list of credit card numbers are needed to be bypassed from inspection

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
Possible values: startURL, cookieConsistency, fieldConsistency, crossSiteScripting, SQLInjection, fieldFormat, CSRFtag, XMLDoSCheck, XMLWSICheck, XMLAttachmentCheck, TotalXMLRequests, creditCardNumber, ContentType



##Outputs

<b>url</b>
Learnt url

<b>name</b>
Learnt field name

<b>fieldType</b>
Learnt field type

<b>fieldFormatMinLength</b>
The minimum allowed length for data in this form field.

<b>fieldFormatMaxLength</b>
The maximum allowed length for data in this form field.

<b>fieldFormatCharMapPCRE</b>
Form field value allowed character map.

<b>valueType</b>
Learnt field value type

<b>value</b>
Learnt field value

<b>hits</b>
Learnt entity hit count

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
Possible values: startURL, cookieConsistency, fieldConsistency, crossSiteScripting, SQLInjection, fieldFormat, CSRFtag, XMLDoSCheck, XMLWSICheck, XMLAttachmentCheck, TotalXMLRequests, creditCardNumber, ContentType

<b>target</b>
Target filename for data to be exported.



