#vpn clientlessAccessProfile

The following operations can be performed on "vpn clientlessAccessProfile":


[add](#add-vpn-clientlessaccessprofile) | [rm](#rm-vpn-clientlessaccessprofile) | [set](#set-vpn-clientlessaccessprofile) | [unset](#unset-vpn-clientlessaccessprofile) | [show](#show-vpn-clientlessaccessprofile)

##add vpn clientlessAccessProfile

Adds a collection of settings that allows clientless access to a given application. Settings include the policies to specify whether to rewrite a URL, rules to find the URLs within various web content-types, and a set of cookies that are required to be present on the client machine.


##Synopsys

add vpn clientlessAccessProfile &lt;profileName>


##Arguments

<b>profileName</b>
Name for the NetScaler Gateway clientless access profile. Must begin with an ASCII alphabetic or underscore (_) character, and must consist only of ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the profile is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my profile" or 'my profile').



##rm vpn clientlessAccessProfile

Removes a clientless access profile.


##Synopsys

rm vpn clientlessAccessProfile &lt;profileName>


##Arguments

<b>profileName</b>
Name of the clientless access profile to remove.



##set vpn clientlessAccessProfile

Modifies the settings for an existing clientless access profile.


##Synopsys

set vpn clientlessAccessProfile &lt;profileName> [-URLRewritePolicyLabel &lt;string>] [-JavaScriptRewritePolicyLabel &lt;string>] [-ReqHdrRewritePolicyLabel &lt;string>] [-ResHdrRewritePolicyLabel &lt;string>] [-RegexForFindingURLinJavaScript &lt;string>] [-RegexForFindingURLinCSS &lt;string>] [-RegexForFindingURLinXComponent &lt;string>] [-RegexForFindingURLinXML &lt;string>] [-RegexForFindingCustomURLs &lt;string>] [-ClientConsumedCookies &lt;string>] [-requirePersistentCookie ( ON | OFF )]


##Arguments

<b>profileName</b>
Name of the clientless access profile to modify.

<b>URLRewritePolicyLabel</b>
Name of the configured URL rewrite policy label. If you do not specify a policy label name, then URLs are not rewritten.

<b>JavaScriptRewritePolicyLabel</b>
Name of the configured JavaScript rewrite policy label.  If you do not specify a policy label name, then JAVA scripts are not rewritten.

<b>ReqHdrRewritePolicyLabel</b>
Name of the configured Request rewrite policy label.  If you do not specify a policy label name, then requests are not rewritten.

<b>ResHdrRewritePolicyLabel</b>
Name of the configured Response rewrite policy label.

<b>RegexForFindingURLinJavaScript</b>
Name of the pattern set that contains the regular expressions, which match the URL in Java script.

<b>RegexForFindingURLinCSS</b>
Name of the pattern set that contains the regular expressions, which match the URL in the CSS.

<b>RegexForFindingURLinXComponent</b>
Name of the pattern set that contains the regular expressions, which match the URL in X Component.

<b>RegexForFindingURLinXML</b>
Name of the pattern set that contains the regular expressions, which match the URL in XML.

<b>RegexForFindingCustomURLs</b>
Name of the pattern set that contains the regular expressions, which match the URLs in the custom content type other than HTML, CSS, XML, XCOMP, and JavaScript. The custom content type should be included in the patset ns_cvpn_custom_content_types.

<b>ClientConsumedCookies</b>
Specify the name of the pattern set containing the names of the cookies, which are allowed between the client and the server. If a pattern set is not specified, NetSCaler Gateway does not allow any cookies between the client and the server. A cookie that is not specified in the pattern set is handled by NetScaler Gateway on behalf of the client.

<b>requirePersistentCookie</b>
Specify whether a persistent session cookie is set and accepted for clientless access. If this parameter is set to ON, COM objects, such as MSOffice, which are invoked by the browser can access the files using clientless access. Use caution because the persistent cookie is stored on the disk.
Possible values: ON, OFF
Default value: OFF



##unset vpn clientlessAccessProfile

Resets the attributes of the specified clientless access profile. Attributes for which a default value is available revert to their default values. Refer to the set vpn clientlessAccessProfile command for a description of the parameters..Refer to the set vpn clientlessAccessProfile command for meanings of the arguments.


##Synopsys

unset vpn clientlessAccessProfile &lt;profileName> [-URLRewritePolicyLabel] [-JavaScriptRewritePolicyLabel] [-ReqHdrRewritePolicyLabel] [-ResHdrRewritePolicyLabel] [-RegexForFindingURLinJavaScript] [-RegexForFindingURLinCSS] [-RegexForFindingURLinXComponent] [-RegexForFindingURLinXML] [-RegexForFindingCustomURLs] [-ClientConsumedCookies] [-requirePersistentCookie]


##show vpn clientlessAccessProfile

Displays information about all the configured clientless access profiles, or displays detailed information about the specified clientless access profile.


##Synopsys

show vpn clientlessAccessProfile [&lt;profileName>]


##Arguments

<b>profileName</b>
Name of the clientless access profile for which to display detailed information.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>URLRewritePolicyLabel</b>
Name of the configured URL rewrite policy label. If you do not specify a policy label name, then URLs are not rewritten.

<b>JavaScriptRewritePolicyLabel</b>
Name of the configured JavaScript rewrite policy label.  If you do not specify a policy label name, then JAVA scripts are not rewritten.

<b>CSSRewritePolicyLabel</b>
The configured CSS rewrite policylabel.

<b>XMLRewritePolicyLabel</b>
The configured XML rewrite policylabel.

<b>XComponentRewritePolicyLabel</b>
The configured X-Component rewrite policylabel.

<b>ReqHdrRewritePolicyLabel</b>
Name of the configured Request rewrite policy label.  If you do not specify a policy label name, then requests are not rewritten.

<b>ResHdrRewritePolicyLabel</b>
Name of the configured Response rewrite policy label.

<b>RegexForFindingURLinJavaScript</b>
Name of the pattern set that contains the regular expressions, which match the URL in Java script.

<b>RegexForFindingURLinCSS</b>
Name of the pattern set that contains the regular expressions, which match the URL in the CSS.

<b>RegexForFindingURLinXComponent</b>
Name of the pattern set that contains the regular expressions, which match the URL in X Component.

<b>RegexForFindingURLinXML</b>
Name of the pattern set that contains the regular expressions, which match the URL in XML.

<b>RegexForFindingCustomURLs</b>
Name of the pattern set that contains the regular expressions, which match the URLs in the custom content type other than HTML, CSS, XML, XCOMP, and JavaScript. The custom content type should be included in the patset ns_cvpn_custom_content_types.

<b>ClientConsumedCookies</b>
Specify the name of the pattern set containing the names of the cookies, which are allowed between the client and the server. If a pattern set is not specified, NetSCaler Gateway does not allow any cookies between the client and the server. A cookie that is not specified in the pattern set is handled by NetScaler Gateway on behalf of the client.

<b>requirePersistentCookie</b>
Specify whether a persistent session cookie is set and accepted for clientless access. If this parameter is set to ON, COM objects, such as MSOffice, which are invoked by the browser can access the files using clientless access. Use caution because the persistent cookie is stored on the disk.

<b>isDefault</b>
A value of true is returned if it is a default vpnclientlessrwprofile.

<b>description</b>
Description of the clientless access profile.

<b>builtin</b>
Flag to determine if vpn clientless rewrite profile is built-in or not

<b>devno</b>

<b>count</b>



