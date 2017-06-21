#appfw profile

The following operations can be performed on "appfw profile":


[add](#add-appfw-profile) | [rm](#rm-appfw-profile) | [set](#set-appfw-profile) | [unset](#unset-appfw-profile) | [bind](#bind-appfw-profile) | [unbind](#unbind-appfw-profile) | [show](#show-appfw-profile) | [stat](#stat-appfw-profile) | [archive](#archive-appfw-profile) | [restore](#restore-appfw-profile)

##add appfw profile

Creates an application firewall profile, which specifies how the application firewall should protect a given type of web content. (A profile is equivalent to an action in other NetScaler features.)


##Synopsys

add appfw profile &lt;name> [-defaults ( basic | advanced )] [-startURLAction &lt;startURLAction> ...] [-contentTypeAction &lt;contentTypeAction> ...] [-inspectContentTypes &lt;inspectContentTypes> ...] [-startURLClosure ( ON | OFF )] [-denyURLAction &lt;denyURLAction> ...] [-RefererHeaderCheck &lt;RefererHeaderCheck>] [-cookieConsistencyAction &lt;cookieConsistencyAction> ...] [-cookieTransforms ( ON | OFF )] [-cookieEncryption &lt;cookieEncryption>] [-cookieProxying ( none | sessionOnly )] [-addCookieFlags &lt;addCookieFlags>] [-fieldConsistencyAction &lt;fieldConsistencyAction> ...] [-CSRFtagAction &lt;CSRFtagAction> ...] [-crossSiteScriptingAction &lt;crossSiteScriptingAction> ...] [-crossSiteScriptingTransformUnsafeHTML ( ON | OFF )] [-crossSiteScriptingCheckCompleteURLs ( ON | OFF )] [-SQLInjectionAction &lt;SQLInjectionAction> ...] [-SQLInjectionTransformSpecialChars ( ON | OFF )] [-SQLInjectionType &lt;SQLInjectionType>] [-SQLInjectionCheckSQLWildChars ( ON | OFF )] [-fieldFormatAction &lt;fieldFormatAction> ...] [-defaultFieldFormatType &lt;string>] [-defaultFieldFormatMinLength &lt;positive_integer>] [-defaultFieldFormatMaxLength &lt;positive_integer>] [-bufferOverflowAction &lt;bufferOverflowAction> ...] [-bufferOverflowMaxURLLength &lt;positive_integer>] [-bufferOverflowMaxHeaderLength &lt;positive_integer>] [-bufferOverflowMaxCookieLength &lt;positive_integer>] [-creditCardAction &lt;creditCardAction> ...] [-creditCard &lt;creditCard> ...] [-creditCardMaxAllowed &lt;positive_integer>] [-creditCardXOut ( ON | OFF )] [-doSecureCreditCardLogging ( ON | OFF )] [-streaming ( ON | OFF )] [-trace ( ON | OFF )] [-requestContentType &lt;string>] [-responseContentType &lt;string>] [-XMLDoSAction &lt;XMLDoSAction> ...] [-XMLFormatAction &lt;XMLFormatAction> ...] [-XMLSQLInjectionAction &lt;XMLSQLInjectionAction> ...] [-XMLSQLInjectionType &lt;XMLSQLInjectionType>] [-XMLSQLInjectionCheckSQLWildChars ( ON | OFF )] [-XMLSQLInjectionParseComments &lt;XMLSQLInjectionParseComments>] [-XMLXSSAction &lt;XMLXSSAction> ...] [-XMLWSIAction &lt;XMLWSIAction> ...] [-XMLAttachmentAction &lt;XMLAttachmentAction> ...] [-XMLValidationAction &lt;XMLValidationAction> ...] [-XMLErrorObject &lt;string>] [-signatures &lt;string>] [-XMLSOAPFaultAction &lt;XMLSOAPFaultAction> ...] [-useHTMLErrorObject ( ON | OFF )] [-errorURL &lt;expression>] [-HTMLErrorObject &lt;string>] [-logEveryPolicyHit ( ON | OFF )] [-stripHtmlComments &lt;stripHtmlComments>] [-stripXmlComments ( none | all )] [-exemptClosureURLsFromSecurityChecks ( ON | OFF )] [-defaultCharSet &lt;string>] [-postBodyLimit &lt;positive_integer>] [-fileUploadMaxNum &lt;positive_integer>] [-canonicalizeHTMLResponse ( ON | OFF )] [-enableFormTagging ( ON | OFF )] [-sessionlessFieldConsistency &lt;sessionlessFieldConsistency>] [-sessionlessURLClosure ( ON | OFF )] [-semicolonFieldSeparator ( ON | OFF )] [-excludeFileUploadFromChecks ( ON | OFF )] [-SQLInjectionParseComments &lt;SQLInjectionParseComments>] [-invalidPercentHandling &lt;invalidPercentHandling>] [-type ( HTML | XML ) ...] [-checkRequestHeaders ( ON | OFF )] [-optimizePartialReqs ( ON | OFF )] [-URLDecodeRequestCookies ( ON | OFF )] [-comment &lt;string>]


##Arguments

<b>name</b>
Name for the profile. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.), pound (#), space ( ), at (@), equals (=), colon (:), and underscore (_) characters. Cannot be changed after the profile is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my profile" or 'my profile').

<b>defaults</b>
Default configuration to apply to the profile. Basic defaults are intended for standard content that requires little further configuration, such as static web site content. Advanced defaults are intended for specialized content that requires significant specialized configuration, such as heavily scripted or dynamic content.
CLI users: When adding an application firewall profile, you can set either the defaults or the type, but not both. To set both options, create the profile by using the add appfw profile command, and then use the set appfw profile command to configure the other option.
Possible values: basic, advanced

<b>startURLAction</b>
One or more Start URL actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Learn - Use the learning engine to generate a list of exceptions to this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -startURLaction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -startURLaction none".
Default value: AS_DEFAULT_DISPOSITION

<b>contentTypeAction</b>
One or more Content-type actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Log - Log violations of this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -contentTypeaction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -contentTypeaction none".
Default value: AS_DEFAULT_CONTENT_TYPE_DISPOSITION

<b>inspectContentTypes</b>
One or more InspectContentType lists. 
* application/x-www-form-urlencoded
* multipart/form-data
* text/x-gwt-rpc
CLI users: To enable, type "set appfw profile -InspectContentTypes" followed by the content types to be inspected.
Default value: AS_DEFAULT_INSPECTION_CONTENT_TYPE

<b>startURLClosure</b>
Toggle  the state of Start URL Closure.
Possible values: ON, OFF
Default value: OFF

<b>denyURLAction</b>
One or more Deny URL actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
NOTE: The Deny URL check takes precedence over the Start URL check. If you enable blocking for the Deny URL check, the application firewall blocks any URL that is explicitly blocked by a Deny URL, even if the same URL would otherwise be allowed by the Start URL check.
CLI users: To enable one or more actions, type "set appfw profile -denyURLaction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -denyURLaction none".
Default value: AS_DEFAULT_DISPOSITION

<b>RefererHeaderCheck</b>
Enable validation of Referer headers. 
Referer validation ensures that a web form that a user sends to your web site originally came from your web site, not an outside attacker. 
Although this parameter is part of the Start URL check, referer validation protects against cross-site request forgery (CSRF) attacks, not Start URL attacks.
Possible values: OFF, if_present, AlwaysExceptStartURLs, AlwaysExceptFirstRequest
Default value: OFF

<b>cookieConsistencyAction</b>
One or more Cookie Consistency actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Learn - Use the learning engine to generate a list of exceptions to this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -cookieConsistencyAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -cookieConsistencyAction none".
Default value: none

<b>cookieTransforms</b>
Perform the specified type of cookie transformation. 
Available settings function as follows: 
* Encryption - Encrypt cookies.
* Proxying - Mask contents of server cookies by sending proxy cookie to users.
* Cookie flags - Flag cookies as HTTP only to prevent scripts on user's browser from accessing and possibly modifying them.
CAUTION: Make sure that this parameter is set to ON if you are configuring any cookie transformations. If it is set to OFF, no cookie transformations are performed regardless of any other settings.
Possible values: ON, OFF
Default value: OFF

<b>cookieEncryption</b>
Type of cookie encryption. Available settings function as follows:
* None - Do not encrypt cookies.
* Decrypt Only - Decrypt encrypted cookies, but do not encrypt cookies.
* Encrypt Session Only - Encrypt session cookies, but not permanent cookies.
* Encrypt All - Encrypt all cookies.
Possible values: none, decryptOnly, encryptSessionOnly, encryptAll
Default value: none

<b>cookieProxying</b>
Cookie proxy setting. Available settings function as follows:
* None - Do not proxy cookies.
* Session Only - Proxy session cookies by using the NetScaler session ID, but do not proxy permanent cookies.
Possible values: none, sessionOnly
Default value: none

<b>addCookieFlags</b>
Add the specified flags to cookies. Available settings function as follows:
* None - Do not add flags to cookies.
* HTTP Only - Add the HTTP Only flag to cookies, which prevents scripts from accessing cookies.
* Secure - Add Secure flag to cookies.
* All - Add both HTTPOnly and Secure flags to cookies.
Possible values: none, httpOnly, secure, all
Default value: none

<b>fieldConsistencyAction</b>
One or more Form Field Consistency actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Learn - Use the learning engine to generate a list of exceptions to this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -fieldConsistencyaction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -fieldConsistencyAction none".
Default value: none

<b>CSRFtagAction</b>
One or more Cross-Site Request Forgery (CSRF) Tagging actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Learn - Use the learning engine to generate a list of exceptions to this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -CSRFTagAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -CSRFTagAction none".
Default value: none

<b>crossSiteScriptingAction</b>
One or more Cross-Site Scripting (XSS) actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Learn - Use the learning engine to generate a list of exceptions to this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -crossSiteScriptingAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -crossSiteScriptingAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>crossSiteScriptingTransformUnsafeHTML</b>
Transform cross-site scripts. This setting configures the application firewall to disable dangerous HTML instead of blocking the request. 
CAUTION: Make sure that this parameter is set to ON if you are configuring any cross-site scripting transformations. If it is set to OFF, no cross-site scripting transformations are performed regardless of any other settings.
Possible values: ON, OFF
Default value: OFF

<b>crossSiteScriptingCheckCompleteURLs</b>
Check complete URLs for cross-site scripts, instead of just the query portions of URLs.
Possible values: ON, OFF
Default value: OFF

<b>SQLInjectionAction</b>
One or more HTML SQL Injection actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Learn - Use the learning engine to generate a list of exceptions to this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -SQLInjectionAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -SQLInjectionAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>SQLInjectionTransformSpecialChars</b>
Transform injected SQL code. This setting configures the application firewall to disable SQL special strings instead of blocking the request. Since most SQL servers require a special string to activate an SQL keyword, in most cases a request that contains injected SQL code is safe if special strings are disabled.
CAUTION: Make sure that this parameter is set to ON if you are configuring any SQL injection transformations. If it is set to OFF, no SQL injection transformations are performed regardless of any other settings.
Possible values: ON, OFF
Default value: OFF

<b>SQLInjectionType</b>
Available SQL injection types. 
-SQLSplChar              : Checks for SQL Special Chars
-SQLKeyword		 : Checks for SQL Keywords
-SQLSplCharANDKeyword    : Checks for both and blocks if both are found
-SQLSplCharORKeyword     : Checks for both and blocks if anyone is found
Possible values: SQLSplChar, SQLKeyword, SQLSplCharORKeyword, SQLSplCharANDKeyword
Default value: SQLSplCharANDKeyword

<b>SQLInjectionCheckSQLWildChars</b>
Check for form fields that contain SQL wild chars .
Possible values: ON, OFF
Default value: OFF

<b>fieldFormatAction</b>
One or more Field Format actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Learn - Use the learning engine to generate a list of suggested web form fields and field format assignments.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -fieldFormatAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -fieldFormatAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>defaultFieldFormatType</b>
Designate a default field type to be applied to web form fields that do not have a field type explicitly assigned to them.

<b>defaultFieldFormatMinLength</b>
Minimum length, in characters, for data entered into a field that is assigned the default field type. 
To disable the minimum and maximum length settings and allow data of any length to be entered into the field, set this parameter to zero (0).
Default value: 0 
Minimum value: 0
Maximum value: 65535

<b>defaultFieldFormatMaxLength</b>
Maximum length, in characters, for data entered into a field that is assigned the default field type.
Default value: 65535 
Minimum value: 1
Maximum value: 65535

<b>bufferOverflowAction</b>
One or more Buffer Overflow actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -bufferOverflowAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -bufferOverflowAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>bufferOverflowMaxURLLength</b>
Maximum length, in characters, for URLs on your protected web sites. Requests with longer URLs are blocked.
Default value: 1024 
Minimum value: 0
Maximum value: 65535

<b>bufferOverflowMaxHeaderLength</b>
Maximum length, in characters, for HTTP headers in requests sent to your protected web sites. Requests with longer headers are blocked.
Default value: 4096 
Minimum value: 0
Maximum value: 65535

<b>bufferOverflowMaxCookieLength</b>
Maximum length, in characters, for cookies sent to your protected web sites. Requests with longer cookies are blocked.
Default value: 4096 
Minimum value: 0
Maximum value: 65535

<b>creditCardAction</b>
One or more Credit Card actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -creditCardAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -creditCardAction none".
Default value: none

<b>creditCard</b>
Credit card types that the application firewall should protect.
Default value: AS_CCARD_DEFAULT_CARD_TYPE

<b>creditCardMaxAllowed</b>
Maximum number of credit card numbers that can appear on a web page served by your protected web sites. Pages that contain more credit card numbers are blocked
Minimum value: 0
Maximum value: 255

<b>creditCardXOut</b>
Mask any credit card number detected in a response by replacing each digit, except the digits in the final group, with the letter "X."
Possible values: ON, OFF
Default value: OFF

<b>doSecureCreditCardLogging</b>
Setting this option logs credit card numbers in the response when the match is found.
Possible values: ON, OFF
Default value: ON

<b>streaming</b>
Setting this option converts content-length form submission requests (requests with content-type "application/x-www-form-urlencoded" or "multipart/form-data") to chunked requests when atleast one of the following protections : SQL injection protection, XSS protection, form field consistency protection, starturl closure, CSRF tagging is enabled. Please make sure that the backend server accepts chunked requests before enabling this option.
Possible values: ON, OFF
Default value: OFF

<b>trace</b>
Toggle  the state of trace
Possible values: ON, OFF
Default value: OFF

<b>requestContentType</b>
Default Content-Type header for requests. 
A Content-Type header can contain 0-255 letters, numbers, and the hyphen (-) and underscore (_) characters.
Default value: NS_S_AS_DEFAULT_REQUEST_CONTENT_TYPE

<b>responseContentType</b>
Default Content-Type header for responses. 
A Content-Type header can contain 0-255 letters, numbers, and the hyphen (-) and underscore (_) characters.
Default value: NS_S_AS_DEFAULT_RESPONSE_CONTENT_TYPE

<b>XMLDoSAction</b>
One or more XML Denial-of-Service (XDoS) actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Learn - Use the learning engine to generate a list of exceptions to this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -XMLDoSAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -XMLDoSAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>XMLFormatAction</b>
One or more XML Format actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -XMLFormatAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -XMLFormatAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>XMLSQLInjectionAction</b>
One or more XML SQL Injection actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -XMLSQLInjectionAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -XMLSQLInjectionAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>XMLSQLInjectionType</b>
Available SQL injection types.
-SQLSplChar              : Checks for SQL Special Chars
-SQLKeyword              : Checks for SQL Keywords
-SQLSplCharANDKeyword    : Checks for both and blocks if both are found
-SQLSplCharORKeyword     : Checks for both and blocks if anyone is found
Possible values: SQLSplChar, SQLKeyword, SQLSplCharORKeyword, SQLSplCharANDKeyword
Default value: SQLSplCharANDKeyword

<b>XMLSQLInjectionCheckSQLWildChars</b>
Check for form fields that contain SQL wild chars .
Possible values: ON, OFF
Default value: OFF

<b>XMLSQLInjectionParseComments</b>
Parse comments in XML Data and exempt those sections of the request that are from the XML SQL Injection check. You must configure the type of comments that the application firewall is to detect and exempt from this security check. Available settings function as follows:
* Check all - Check all content.
* ANSI - Exempt content that is part of an ANSI (Mozilla-style) comment. 
* Nested - Exempt content that is part of a nested (Microsoft-style) comment.
* ANSI Nested - Exempt content that is part of any type of comment.
Possible values: checkall, ansi, nested, ansinested
Default value: checkall

<b>XMLXSSAction</b>
One or more XML Cross-Site Scripting actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -XMLXSSAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -XMLXSSAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>XMLWSIAction</b>
One or more Web Services Interoperability (WSI) actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Learn - Use the learning engine to generate a list of exceptions to this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -XMLWSIAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -XMLWSIAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>XMLAttachmentAction</b>
One or more XML Attachment actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Learn - Use the learning engine to generate a list of exceptions to this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -XMLAttachmentAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -XMLAttachmentAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>XMLValidationAction</b>
One or more XML Validation actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check. 
CLI users: To enable one or more actions, type "set appfw profile -XMLValidationAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -XMLValidationAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>XMLErrorObject</b>
Name to assign to the XML Error Object, which the application firewall displays when a user request is blocked.
Must begin with a letter, number, or the underscore character \\(_\\), and must contain only letters, numbers, and the hyphen \\(-\\), period \\(.\\) pound \\(\\#\\), space \\( \\), at (@), equals \\(=\\), colon \\(:\\), and underscore characters. Cannot be changed after the XML error object is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks \\(for example, "my XML error object" or 'my XML error object'\\).
Default value: NS_S_AS_ERROR_OBJECT_DEFAULT

<b>signatures</b>
Object name for signatures.
This check is applicable to Profile Type: HTML, XML. 
Default value: NS_S_AS_CUSTOM_OBJECT_DEFAULT

<b>XMLSOAPFaultAction</b>
One or more XML SOAP Fault Filtering actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
* Remove - Remove all violations for this security check.
CLI users: To enable one or more actions, type "set appfw profile -XMLSOAPFaultAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -XMLSOAPFaultAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>useHTMLErrorObject</b>
Send an imported HTML Error object to a user when a request is blocked, instead of redirecting the user to the designated Error URL.
Possible values: ON, OFF
Default value: OFF

<b>errorURL</b>
URL that application firewall uses as the Error URL.
Default value: NS_S_AS_ERROR_URL_DEFAULT

<b>HTMLErrorObject</b>
Name to assign to the HTML Error Object. 
Must begin with a letter, number, or the underscore character \\(_\\), and must contain only letters, numbers, and the hyphen \\(-\\), period \\(.\\) pound \\(\\#\\), space \\( \\), at (@), equals \\(=\\), colon \\(:\\), and underscore characters. Cannot be changed after the HTML error object is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks \\(for example, "my HTML error object" or 'my HTML error object'\\).
Default value: NS_S_AS_ERROR_OBJECT_DEFAULT

<b>logEveryPolicyHit</b>
Log every profile match, regardless of security checks results.
Possible values: ON, OFF
Default value: OFF

<b>stripHtmlComments</b>
Strip HTML comments before forwarding a web page sent by a protected web site in response to a user request.
Possible values: none, all, exclude_script_tag
Default value: none

<b>stripXmlComments</b>
Strip XML comments before forwarding a web page sent by a protected web site in response to a user request.
Possible values: none, all
Default value: none

<b>exemptClosureURLsFromSecurityChecks</b>
Exempt URLs that pass the Start URL closure check from SQL injection, cross-site script, field format and field consistency security checks at locations other than headers.
Possible values: ON, OFF
Default value: ON

<b>defaultCharSet</b>
Default character set for protected web pages. Web pages sent by your protected web sites in response to user requests are assigned this character set if the page does not already specify a character set. The character sets supported by the application firewall are: 
* iso-8859-1 (English US)
* big5 (Chinese Traditional)
* gb2312 (Chinese Simplified)
* sjis (Japanese Shift-JIS)
* euc-jp (Japanese EUC-JP)
* iso-8859-9 (Turkish)
* utf-8 (Unicode)
* euc-kr (Korean)
Default value: NS_S_AS_CHARSET_DEFAULT
Maximum value: 31

<b>postBodyLimit</b>
Maximum allowed HTTP post body size, in bytes.
Default value: 20000000 
Minimum value: 0
Maximum value: 1000000000

<b>fileUploadMaxNum</b>
Maximum allowed number of file uploads per form-submission request. The maximum setting (65535) allows an unlimited number of uploads.
Default value: 65535 
Minimum value: 0
Maximum value: 65535

<b>canonicalizeHTMLResponse</b>
Perform HTML entity encoding for any special characters in responses sent by your protected web sites.
Possible values: ON, OFF
Default value: ON

<b>enableFormTagging</b>
Enable tagging of web form fields for use by the Form Field Consistency and CSRF Form Tagging checks.
Possible values: ON, OFF
Default value: ON

<b>sessionlessFieldConsistency</b>
Perform sessionless Field Consistency Checks.
Possible values: OFF, ON, postOnly
Default value: OFF

<b>sessionlessURLClosure</b>
Enable session less URL Closure Checks.
This check is applicable to Profile Type: HTML. 
Possible values: ON, OFF
Default value: OFF

<b>semicolonFieldSeparator</b>
Allow ';' as a form field separator in URL queries and POST form bodies. 
Possible values: ON, OFF
Default value: OFF

<b>excludeFileUploadFromChecks</b>
Exclude uploaded files from Form checks.
Possible values: ON, OFF
Default value: OFF

<b>SQLInjectionParseComments</b>
Parse HTML comments and exempt them from the HTML SQL Injection check. You must specify the type of comments that the application firewall is to detect and exempt from this security check. Available settings function as follows:
* Check all - Check all content.
* ANSI - Exempt content that is part of an ANSI (Mozilla-style) comment. 
* Nested - Exempt content that is part of a nested (Microsoft-style) comment.
* ANSI Nested - Exempt content that is part of any type of comment.
Possible values: checkall, ansi, nested, ansinested
Default value: AS_DEFAULT_SQLINJECTIONPARSECOMMENTS

<b>invalidPercentHandling</b>
Configure the method that the application firewall uses to handle percent-encoded names and values. Available settings function as follows: 
* apache_mode - Apache format.
* asp_mode - Microsoft ASP format.
* secure_mode - Secure format.
Possible values: apache_mode, asp_mode, secure_mode
Default value: secure_mode

<b>type</b>
Application firewall profile type, which controls which security checks and settings are applied to content that is filtered with the profile. Available settings function as follows:
* HTML - HTML-based web sites.
* XML - XML-based web sites and services.
* HTML XML (Web 2.0) - Sites that contain both HTML and XML content, such as ATOM feeds, blogs, and RSS feeds.
Default value: HTML

<b>checkRequestHeaders</b>
Check request headers as well as web forms for injected SQL and cross-site scripts.
Possible values: ON, OFF
Default value: OFF

<b>optimizePartialReqs</b>
Optimize handle of HTTP partial requests i.e. those with range headers.
Available settings are as follows: 
* ON  - Partial requests by the client result in partial requests to the backend server in most cases.
* OFF - Partial requests by the client are changed to full requests to the backend server
Possible values: ON, OFF
Default value: ON

<b>URLDecodeRequestCookies</b>
URL Decode request cookies before subjecting them to SQL and cross-site scripting checks.
Possible values: ON, OFF
Default value: OFF

<b>comment</b>
Any comments about the purpose of profile, or other useful information about the profile.



##rm appfw profile

Removes the specified application firewall profile.


##Synopsys

rm appfw profile &lt;name>


##Arguments

<b>name</b>
Name of the profile.



##set appfw profile

Modifies the specified parameters of the specified application firewall profile.


##Synopsys

set appfw profile &lt;name> [-startURLAction &lt;startURLAction> ...] [-contentTypeAction &lt;contentTypeAction> ...] [-inspectContentTypes &lt;inspectContentTypes> ...] [-startURLClosure ( ON | OFF )] [-denyURLAction &lt;denyURLAction> ...] [-RefererHeaderCheck &lt;RefererHeaderCheck>] [-cookieConsistencyAction &lt;cookieConsistencyAction> ...] [-cookieTransforms ( ON | OFF )] [-cookieEncryption &lt;cookieEncryption>] [-cookieProxying ( none | sessionOnly )] [-addCookieFlags &lt;addCookieFlags>] [-fieldConsistencyAction &lt;fieldConsistencyAction> ...] [-CSRFtagAction &lt;CSRFtagAction> ...] [-crossSiteScriptingAction &lt;crossSiteScriptingAction> ...] [-crossSiteScriptingTransformUnsafeHTML ( ON | OFF )] [-crossSiteScriptingCheckCompleteURLs ( ON | OFF )] [-SQLInjectionAction &lt;SQLInjectionAction> ...] [-SQLInjectionTransformSpecialChars ( ON | OFF )] [-SQLInjectionType &lt;SQLInjectionType>] [-SQLInjectionCheckSQLWildChars ( ON | OFF )] [-fieldFormatAction &lt;fieldFormatAction> ...] [-defaultFieldFormatType &lt;string>] [-defaultFieldFormatMinLength &lt;positive_integer>] [-defaultFieldFormatMaxLength &lt;positive_integer>] [-bufferOverflowAction &lt;bufferOverflowAction> ...] [-bufferOverflowMaxURLLength &lt;positive_integer>] [-bufferOverflowMaxHeaderLength &lt;positive_integer>] [-bufferOverflowMaxCookieLength &lt;positive_integer>] [-creditCardAction &lt;creditCardAction> ...] [-creditCard &lt;creditCard> ...] [-creditCardMaxAllowed &lt;positive_integer>] [-creditCardXOut ( ON | OFF )] [-doSecureCreditCardLogging ( ON | OFF )] [-streaming ( ON | OFF )] [-trace ( ON | OFF )] [-requestContentType &lt;string>] [-responseContentType &lt;string>] [-XMLDoSAction &lt;XMLDoSAction> ...] [-XMLFormatAction &lt;XMLFormatAction> ...] [-XMLSQLInjectionAction &lt;XMLSQLInjectionAction> ...] [-XMLSQLInjectionType &lt;XMLSQLInjectionType>] [-XMLSQLInjectionCheckSQLWildChars ( ON | OFF )] [-XMLSQLInjectionParseComments &lt;XMLSQLInjectionParseComments>] [-XMLXSSAction &lt;XMLXSSAction> ...] [-XMLWSIAction &lt;XMLWSIAction> ...] [-XMLAttachmentAction &lt;XMLAttachmentAction> ...] [-XMLValidationAction &lt;XMLValidationAction> ...] [-XMLErrorObject &lt;string>] [-signatures &lt;string>] [-XMLSOAPFaultAction &lt;XMLSOAPFaultAction> ...] [-useHTMLErrorObject ( ON | OFF )] [-errorURL &lt;expression>] [-HTMLErrorObject &lt;string>] [-logEveryPolicyHit ( ON | OFF )] [-stripHtmlComments &lt;stripHtmlComments>] [-stripXmlComments ( none | all )] [-exemptClosureURLsFromSecurityChecks ( ON | OFF )] [-defaultCharSet &lt;string>] [-postBodyLimit &lt;positive_integer>] [-fileUploadMaxNum &lt;positive_integer>] [-canonicalizeHTMLResponse ( ON | OFF )] [-enableFormTagging ( ON | OFF )] [-sessionlessFieldConsistency &lt;sessionlessFieldConsistency>] [-sessionlessURLClosure ( ON | OFF )] [-semicolonFieldSeparator ( ON | OFF )] [-excludeFileUploadFromChecks ( ON | OFF )] [-SQLInjectionParseComments &lt;SQLInjectionParseComments>] [-invalidPercentHandling &lt;invalidPercentHandling>] [-type ( HTML | XML ) ...] [-checkRequestHeaders ( ON | OFF )] [-optimizePartialReqs ( ON | OFF )] [-URLDecodeRequestCookies ( ON | OFF )] [-comment &lt;string>]


##Arguments

<b>name</b>
Name of the profile that you want to modify.

<b>startURLAction</b>
One or more Start URL actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Learn - Use the learning engine to generate a list of exceptions to this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -startURLaction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -startURLaction none".
Default value: AS_DEFAULT_DISPOSITION

<b>contentTypeAction</b>
One or more Content-type actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Log - Log violations of this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -contentTypeaction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -contentTypeaction none".
Default value: AS_DEFAULT_CONTENT_TYPE_DISPOSITION

<b>inspectContentTypes</b>
One or more InspectContentType lists. 
* application/x-www-form-urlencoded
* multipart/form-data
* text/x-gwt-rpc
CLI users: To enable, type "set appfw profile -InspectContentTypes" followed by the content types to be inspected.
Default value: AS_DEFAULT_INSPECTION_CONTENT_TYPE

<b>startURLClosure</b>
Toggle  the state of Start URL Closure.
Possible values: ON, OFF
Default value: OFF

<b>denyURLAction</b>
One or more Deny URL actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
NOTE: The Deny URL check takes precedence over the Start URL check. If you enable blocking for the Deny URL check, the application firewall blocks any URL that is explicitly blocked by a Deny URL, even if the same URL would otherwise be allowed by the Start URL check.
CLI users: To enable one or more actions, type "set appfw profile -denyURLaction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -denyURLaction none".
Default value: AS_DEFAULT_DISPOSITION

<b>RefererHeaderCheck</b>
Enable validation of Referer headers. 
Referer validation ensures that a web form that a user sends to your web site originally came from your web site, not an outside attacker. 
Although this parameter is part of the Start URL check, referer validation protects against cross-site request forgery (CSRF) attacks, not Start URL attacks.
Possible values: OFF, if_present, AlwaysExceptStartURLs, AlwaysExceptFirstRequest
Default value: OFF

<b>cookieConsistencyAction</b>
One or more Cookie Consistency actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Learn - Use the learning engine to generate a list of exceptions to this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -cookieConsistencyAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -cookieConsistencyAction none".
Default value: none

<b>cookieTransforms</b>
Perform the specified type of cookie transformation. 
Available settings function as follows: 
* Encryption - Encrypt cookies.
* Proxying - Mask contents of server cookies by sending proxy cookie to users.
* Cookie flags - Flag cookies as HTTP only to prevent scripts on user's browser from accessing and possibly modifying them.
CAUTION: Make sure that this parameter is set to ON if you are configuring any cookie transformations. If it is set to OFF, no cookie transformations are performed regardless of any other settings.
Possible values: ON, OFF

<b>cookieEncryption</b>
Type of cookie encryption. Available settings function as follows:
* None - Do not encrypt cookies.
* Decrypt Only - Decrypt encrypted cookies, but do not encrypt cookies.
* Encrypt Session Only - Encrypt session cookies, but not permanent cookies.
* Encrypt All - Encrypt all cookies.
Possible values: none, decryptOnly, encryptSessionOnly, encryptAll
Default value: none

<b>cookieProxying</b>
Cookie proxy setting. Available settings function as follows:
* None - Do not proxy cookies.
* Session Only - Proxy session cookies by using the NetScaler session ID, but do not proxy permanent cookies.
Possible values: none, sessionOnly
Default value: none

<b>addCookieFlags</b>
Add HttpOnly and Secure flags to cookies
Possible values: none, httpOnly, secure, all
Default value: none

<b>fieldConsistencyAction</b>
One or more Form Field Consistency actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Learn - Use the learning engine to generate a list of exceptions to this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -fieldConsistencyaction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -fieldConsistencyAction none".
Default value: none

<b>CSRFtagAction</b>
One or more Cross-Site Request Forgery (CSRF) Tagging actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Learn - Use the learning engine to generate a list of exceptions to this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -CSRFTagAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -CSRFTagAction none".
Default value: none

<b>crossSiteScriptingAction</b>
One or more Cross-Site Scripting (XSS) actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Learn - Use the learning engine to generate a list of exceptions to this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -crossSiteScriptingAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -crossSiteScriptingAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>crossSiteScriptingTransformUnsafeHTML</b>
Transform cross-site scripts. This setting configures the application firewall to disable dangerous HTML instead of blocking the request. 
CAUTION: Make sure that this parameter is set to ON if you are configuring any cross-site scripting transformations. If it is set to OFF, no cross-site scripting transformations are performed regardless of any other settings.
Possible values: ON, OFF

<b>crossSiteScriptingCheckCompleteURLs</b>
Check complete URLs for cross-site scripts, instead of just the query portions of URLs.
Possible values: ON, OFF

<b>SQLInjectionAction</b>
One or more HTML SQL Injection actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Learn - Use the learning engine to generate a list of exceptions to this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -SQLInjectionAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -SQLInjectionAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>SQLInjectionTransformSpecialChars</b>
Transform injected SQL code. This setting configures the application firewall to disable SQL special strings instead of blocking the request. Since most SQL servers require a special string to activate an SQL keyword, in most cases a request that contains injected SQL code is safe if special strings are disabled.
CAUTION: Make sure that this parameter is set to ON if you are configuring any SQL injection transformations. If it is set to OFF, no SQL injection transformations are performed regardless of any other settings.
Possible values: ON, OFF

<b>SQLInjectionType</b>
Available SQL injection types. 
-SQLSplChar              : Checks for SQL Special Chars
-SQLKeyword		 : Checks for SQL Keywords
-SQLSplCharANDKeyword    : Checks for both and blocks if both are found
-SQLSplCharORKeyword     : Checks for both and blocks if anyone is found
Possible values: SQLSplChar, SQLKeyword, SQLSplCharORKeyword, SQLSplCharANDKeyword

<b>SQLInjectionCheckSQLWildChars</b>
Check for form fields that contain SQL wild chars .
Possible values: ON, OFF

<b>fieldFormatAction</b>
One or more Field Format actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Learn - Use the learning engine to generate a list of suggested web form fields and field format assignments.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -fieldFormatAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -fieldFormatAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>defaultFieldFormatType</b>
Designate a default field type to be applied to web form fields that do not have a field type explicitly assigned to them.

<b>defaultFieldFormatMinLength</b>
Minimum length, in characters, for data entered into a field that is assigned the default field type. 
To disable the minimum and maximum length settings and allow data of any length to be entered into the field, set this parameter to zero (0).
Default value: 0 
Minimum value: 0
Maximum value: 65535

<b>defaultFieldFormatMaxLength</b>
Maximum length, in characters, for data entered into a field that is assigned the default field type.
Default value: 65535 
Minimum value: 1
Maximum value: 65535

<b>bufferOverflowAction</b>
One or more Buffer Overflow actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -bufferOverflowAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -bufferOverflowAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>bufferOverflowMaxURLLength</b>
Maximum length, in characters, for URLs on your protected web sites. Requests with longer URLs are blocked.
Default value: 1024 
Minimum value: 0
Maximum value: 65535

<b>bufferOverflowMaxHeaderLength</b>
Maximum length, in characters, for HTTP headers in requests sent to your protected web sites. Requests with longer headers are blocked.
Default value: 4096 
Minimum value: 0
Maximum value: 65535

<b>bufferOverflowMaxCookieLength</b>
Maximum length, in characters, for cookies sent to your protected web sites. Requests with longer cookies are blocked.
Default value: 4096 
Minimum value: 0
Maximum value: 65535

<b>creditCardAction</b>
One or more Credit Card actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -creditCardAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -creditCardAction none".
Default value: none

<b>creditCard</b>
Credit card types that the application firewall should protect.
Default value: AS_CCARD_DEFAULT_CARD_TYPE

<b>creditCardMaxAllowed</b>
Maximum number of credit card numbers that can appear on a web page served by your protected web sites. Pages that contain more credit card numbers are blocked
Minimum value: 0
Maximum value: 255

<b>creditCardXOut</b>
Mask any credit card number detected in a response by replacing each digit, except the digits in the final group, with the letter "X."
Possible values: ON, OFF

<b>doSecureCreditCardLogging</b>
Setting this option logs credit card numbers in the response when the match is found.
Possible values: ON, OFF

<b>streaming</b>
Setting this option converts content-length form submission requests (requests with content-type "application/x-www-form-urlencoded" or "multipart/form-data") to chunked requests when atleast one of the following protections : SQL injection protection, XSS protection, form field consistency protection, starturl closure, CSRF tagging is enabled. Please make sure that the backend server accepts chunked requests before enabling this option.
Possible values: ON, OFF

<b>trace</b>
Toggle  the state of trace
Possible values: ON, OFF

<b>requestContentType</b>
Default Content-Type header for requests. 
A Content-Type header can contain 0-255 letters, numbers, and the hyphen (-) and underscore (_) characters.
Default value: NS_S_AS_DEFAULT_REQUEST_CONTENT_TYPE

<b>responseContentType</b>
Default Content-Type header for responses. 
A Content-Type header can contain 0-255 letters, numbers, and the hyphen (-) and underscore (_) characters.
Default value: NS_S_AS_DEFAULT_RESPONSE_CONTENT_TYPE

<b>XMLDoSAction</b>
One or more XML Denial-of-Service (XDoS) actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Learn - Use the learning engine to generate a list of exceptions to this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -XMLDoSAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -XMLDoSAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>XMLFormatAction</b>
One or more XML Format actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -XMLFormatAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -XMLFormatAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>XMLSQLInjectionAction</b>
One or more XML SQL Injection actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -XMLSQLInjectionAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -XMLSQLInjectionAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>XMLSQLInjectionType</b>
Available SQL injection types.
-SQLSplChar              : Checks for SQL Special Chars
-SQLKeyword              : Checks for SQL Keywords
-SQLSplCharANDKeyword    : Checks for both and blocks if both are found
-SQLSplCharORKeyword     : Checks for both and blocks if anyone is found
Possible values: SQLSplChar, SQLKeyword, SQLSplCharORKeyword, SQLSplCharANDKeyword

<b>XMLSQLInjectionCheckSQLWildChars</b>
Check for form fields that contain SQL wild chars .
Possible values: ON, OFF

<b>XMLSQLInjectionParseComments</b>
Parse comments in XML Data and exempt those sections of the request that are from the XML SQL Injection check. You must configure the type of comments that the application firewall is to detect and exempt from this security check. Available settings function as follows:
* Check all - Check all content.
* ANSI - Exempt content that is part of an ANSI (Mozilla-style) comment. 
* Nested - Exempt content that is part of a nested (Microsoft-style) comment.
* ANSI Nested - Exempt content that is part of any type of comment.
Possible values: checkall, ansi, nested, ansinested
Default value: checkall

<b>XMLXSSAction</b>
One or more XML Cross-Site Scripting actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -XMLXSSAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -XMLXSSAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>XMLWSIAction</b>
One or more Web Services Interoperability (WSI) actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Learn - Use the learning engine to generate a list of exceptions to this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -XMLWSIAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -XMLWSIAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>XMLAttachmentAction</b>
One or more XML Attachment actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Learn - Use the learning engine to generate a list of exceptions to this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
CLI users: To enable one or more actions, type "set appfw profile -XMLAttachmentAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -XMLAttachmentAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>XMLValidationAction</b>
One or more XML Validation actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check. 
CLI users: To enable one or more actions, type "set appfw profile -XMLValidationAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -XMLValidationAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>XMLErrorObject</b>
Name to assign to the XML Error Object, which the application firewall displays when a user request is blocked.
Must begin with a letter, number, or the underscore character \\(_\\), and must contain only letters, numbers, and the hyphen \\(-\\), period \\(.\\) pound \\(\\#\\), space \\( \\), at (@), equals \\(=\\), colon \\(:\\), and underscore characters. Cannot be changed after the XML error object is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks \\(for example, "my XML error object" or 'my XML error object'\\).
Default value: NS_S_AS_ERROR_OBJECT_DEFAULT

<b>signatures</b>
Object name for signatures.
This check is applicable to Profile Type: HTML, XML. 
Default value: NS_S_AS_CUSTOM_OBJECT_DEFAULT

<b>XMLSOAPFaultAction</b>
One or more XML SOAP Fault Filtering actions. Available settings function as follows:
* Block - Block connections that violate this security check.
* Log - Log violations of this security check.
* Stats - Generate statistics for this security check.
* None - Disable all actions for this security check.
* Remove - Remove all violations for this security check.
CLI users: To enable one or more actions, type "set appfw profile -XMLSOAPFaultAction" followed by the actions to be enabled. To turn off all actions, type "set appfw profile -XMLSOAPFaultAction none".
Default value: AS_DEFAULT_DISPOSITION

<b>useHTMLErrorObject</b>
Send an imported HTML Error object to a user when a request is blocked, instead of redirecting the user to the designated Error URL.
Possible values: ON, OFF

<b>errorURL</b>
URL that application firewall uses as the Error URL.
Default value: NS_S_AS_ERROR_URL_DEFAULT

<b>HTMLErrorObject</b>
Name to assign to the HTML Error Object. 
Must begin with a letter, number, or the underscore character \\(_\\), and must contain only letters, numbers, and the hyphen \\(-\\), period \\(.\\) pound \\(\\#\\), space \\( \\), at (@), equals \\(=\\), colon \\(:\\), and underscore characters. Cannot be changed after the HTML error object is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks \\(for example, "my HTML error object" or 'my HTML error object'\\).
Default value: NS_S_AS_ERROR_OBJECT_DEFAULT

<b>logEveryPolicyHit</b>
Log every profile match, regardless of security checks results.
Possible values: ON, OFF

<b>stripHtmlComments</b>
Strip HTML comments before forwarding a web page sent by a protected web site in response to a user request.
Possible values: none, all, exclude_script_tag

<b>stripXmlComments</b>
Strip XML comments before forwarding a web page sent by a protected web site in response to a user request.
Possible values: none, all

<b>exemptClosureURLsFromSecurityChecks</b>
Exempt URLs that pass the Start URL closure check from SQL injection, cross-site script, field format and field consistency security checks at locations other than headers.
Possible values: ON, OFF

<b>defaultCharSet</b>
Default character set for protected web pages. Web pages sent by your protected web sites in response to user requests are assigned this character set if the page does not already specify a character set. The character sets supported by the application firewall are: 
* iso-8859-1 (English US)
* big5 (Chinese Traditional)
* gb2312 (Chinese Simplified)
* sjis (Japanese Shift-JIS)
* euc-jp (Japanese EUC-JP)
* iso-8859-9 (Turkish)
* utf-8 (Unicode)
* euc-kr (Korean)
Default value: NS_S_AS_CHARSET_DEFAULT
Maximum value: 31

<b>postBodyLimit</b>
Maximum allowed HTTP post body size, in bytes.
Default value: 20000000 
Minimum value: 0
Maximum value: 1000000000

<b>fileUploadMaxNum</b>
Maximum allowed number of file uploads per form-submission request. The maximum setting (65535) allows an unlimited number of uploads.
Default value: 65535 
Minimum value: 0
Maximum value: 65535

<b>canonicalizeHTMLResponse</b>
Perform HTML entity encoding for any special characters in responses sent by your protected web sites.
Possible values: ON, OFF
Default value: ON

<b>enableFormTagging</b>
Enable tagging of web form fields for use by the Form Field Consistency and CSRF Form Tagging checks.
Possible values: ON, OFF
Default value: ON

<b>sessionlessFieldConsistency</b>
Perform sessionless Field Consistency Checks.
Possible values: OFF, ON, postOnly
Default value: OFF

<b>sessionlessURLClosure</b>
Enable session less URL Closure Checks.
This check is applicable to Profile Type: HTML. 
Possible values: ON, OFF
Default value: OFF

<b>semicolonFieldSeparator</b>
Allow ';' as a form field separator in URL queries and POST form bodies. 
Possible values: ON, OFF
Default value: OFF

<b>excludeFileUploadFromChecks</b>
Exclude uploaded files from Form checks.
Possible values: ON, OFF
Default value: OFF

<b>SQLInjectionParseComments</b>
Parse HTML comments and exempt them from the HTML SQL Injection check. You must specify the type of comments that the application firewall is to detect and exempt from this security check. Available settings function as follows:
* Check all - Check all content.
* ANSI - Exempt content that is part of an ANSI (Mozilla-style) comment. 
* Nested - Exempt content that is part of a nested (Microsoft-style) comment.
* ANSI Nested - Exempt content that is part of any type of comment.
Possible values: checkall, ansi, nested, ansinested
Default value: AS_DEFAULT_SQLINJECTIONPARSECOMMENTS

<b>invalidPercentHandling</b>
Configure the method that the application firewall uses to handle percent-encoded names and values. Available settings function as follows: 
* apache_mode - Apache format.
* asp_mode - Microsoft ASP format.
* secure_mode - Secure format.
Possible values: apache_mode, asp_mode, secure_mode
Default value: secure_mode

<b>type</b>
Application firewall profile type, which controls which security checks and settings are applied to content that is filtered with the profile. Available settings function as follows:
* HTML - HTML-based web sites.
* XML - XML-based web sites and services.
* HTML XML (Web 2.0) - Sites that contain both HTML and XML content, such as ATOM feeds, blogs, and RSS feeds.
Default value: HTML

<b>checkRequestHeaders</b>
Check request headers as well as web forms for injected SQL and cross-site scripts.
Possible values: ON, OFF
Default value: OFF

<b>optimizePartialReqs</b>
Optimize handle of HTTP partial requests i.e. those with range headers.
Available settings are as follows: 
* ON  - Partial requests by the client result in partial requests to the backend server in most cases.
* OFF - Partial requests by the client are changed to full requests to the backend server
Possible values: ON, OFF

<b>URLDecodeRequestCookies</b>
URL Decode request cookies before subjecting them to SQL and cross-site scripting checks.
Possible values: ON, OFF
Default value: OFF

<b>comment</b>
Any comments about the purpose of profile, or other useful information about the profile.



##unset appfw profile

Use this command to remove appfw profile settings.Refer to the set appfw profile command for meanings of the arguments.


##Synopsys

unset appfw profile &lt;name> [-startURLAction] [-contentTypeAction] [-inspectContentTypes] [-startURLClosure] [-denyURLAction] [-RefererHeaderCheck] [-cookieConsistencyAction] [-cookieTransforms] [-cookieEncryption] [-cookieProxying] [-addCookieFlags] [-fieldConsistencyAction] [-CSRFtagAction] [-crossSiteScriptingAction] [-crossSiteScriptingTransformUnsafeHTML] [-crossSiteScriptingCheckCompleteURLs] [-SQLInjectionAction] [-SQLInjectionTransformSpecialChars] [-SQLInjectionType] [-SQLInjectionCheckSQLWildChars] [-fieldFormatAction] [-defaultFieldFormatType] [-defaultFieldFormatMinLength] [-defaultFieldFormatMaxLength] [-bufferOverflowAction] [-bufferOverflowMaxURLLength] [-bufferOverflowMaxHeaderLength] [-bufferOverflowMaxCookieLength] [-creditCardAction] [-creditCard] [-creditCardMaxAllowed] [-creditCardXOut] [-doSecureCreditCardLogging] [-streaming] [-trace] [-requestContentType] [-responseContentType] [-XMLDoSAction] [-XMLFormatAction] [-XMLSQLInjectionAction] [-XMLSQLInjectionType] [-XMLSQLInjectionCheckSQLWildChars] [-XMLSQLInjectionParseComments] [-XMLXSSAction] [-XMLWSIAction] [-XMLAttachmentAction] [-XMLValidationAction] [-XMLErrorObject] [-signatures] [-XMLSOAPFaultAction] [-useHTMLErrorObject] [-errorURL] [-HTMLErrorObject] [-logEveryPolicyHit] [-stripHtmlComments] [-stripXmlComments] [-exemptClosureURLsFromSecurityChecks] [-defaultCharSet] [-postBodyLimit] [-fileUploadMaxNum] [-canonicalizeHTMLResponse] [-enableFormTagging] [-sessionlessFieldConsistency] [-sessionlessURLClosure] [-semicolonFieldSeparator] [-excludeFileUploadFromChecks] [-SQLInjectionParseComments] [-invalidPercentHandling] [-type] [-checkRequestHeaders] [-optimizePartialReqs] [-URLDecodeRequestCookies] [-comment]


##bind appfw profile

Binds the specified exemption (relaxation) or rule to the specified application firewall profile. NOTE: You should not attempt to bind more than one exemption or rule at a time by using this command.


##Synopsys

bind appfw profile &lt;name> (-startURL &lt;expression> | -denyURL &lt;expression> | (-fieldConsistency &lt;string>  &lt;formActionURL>  [-isRegex ( REGEX | NOTREGEX )]) | (-cookieConsistency &lt;string>  [-isRegex ( REGEX | NOTREGEX )]) | (-SQLInjection &lt;string>  &lt;formActionURL>  [-isRegex ( REGEX | NOTREGEX )]  [-location &lt;location>]  [-valueType &lt;valueType>  &lt;valueExpression>  [-isValueRegex ( REGEX | NOTREGEX )]]) | (-CSRFTag &lt;expression>  &lt;CSRFFormActionURL>) | (-crossSiteScripting &lt;string>  &lt;formActionURL>  [-isRegex ( REGEX | NOTREGEX )]  [-location &lt;location>]  [-valueType &lt;valueType>  &lt;valueExpression>  [-isValueRegex ( REGEX | NOTREGEX )]]) | (-fieldFormat &lt;string>  &lt;formActionURL>  &lt;fieldType>  [-fieldFormatMinLength &lt;positive_integer>]  [-fieldFormatMaxLength &lt;positive_integer>]  [-isRegex ( REGEX | NOTREGEX )]) | (-safeObject &lt;string>  &lt;expression>  &lt;maxMatchLength>  [-action &lt;action> ...]) | -trustedLearningClients &lt;ip_addr[/prefix]|ipv6_addr[/prefix]|*> | (-XMLDoSURL &lt;expression>  [-XMLMaxElementDepthCheck ( ON | OFF )  [-XMLMaxElementDepth &lt;positive_integer>]]  [-XMLMaxElementNameLengthCheck ( ON | OFF )  [-XMLMaxElementNameLength &lt;positive_integer>]]  [-XMLMaxElementsCheck ( ON | OFF )  [-XMLMaxElements &lt;positive_integer>]]  [-XMLMaxElementChildrenCheck ( ON | OFF )  [-XMLMaxElementChildren &lt;positive_integer>]]  [-XMLMaxAttributesCheck ( ON | OFF )  [-XMLMaxAttributes &lt;positive_integer>]]  [-XMLMaxAttributeNameLengthCheck ( ON | OFF )  [-XMLMaxAttributeNameLength &lt;positive_integer>]]  [-XMLMaxAttributeValueLengthCheck ( ON | OFF )  [-XMLMaxAttributeValueLength &lt;positive_integer>]]  [-XMLMaxCharDATALengthCheck ( ON | OFF )  [-XMLMaxCharDATALength &lt;positive_integer>]]  [-XMLMaxFileSizeCheck ( ON | OFF )  [-XMLMaxFileSize &lt;positive_integer>]]  [-XMLMinFileSizeCheck ( ON | OFF )  [-XMLMinFileSize &lt;positive_integer>]]  [-XMLBlockPI ( ON | OFF )]  [-XMLBlockDTD ( ON | OFF )]  [-XMLBlockExternalEntities ( ON | OFF )]  [-XMLMaxEntityExpansionsCheck ( ON | OFF )  [-XMLMaxEntityExpansions &lt;positive_integer>]]  [-XMLMaxEntityExpansionDepthCheck ( ON | OFF )  [-XMLMaxEntityExpansionDepth &lt;positive_integer>]]  [-XMLMaxNamespacesCheck ( ON | OFF )  [-XMLMaxNamespaces &lt;positive_integer>]]  [-XMLMaxNamespaceUriLengthCheck ( ON | OFF )  [-XMLMaxNamespaceUriLength &lt;positive_integer>]]  [-XMLSOAPArrayCheck ( ON | OFF )  [-XMLMaxSOAPArraySize &lt;positive_integer>]  [-XMLMaxSOAPArrayRank &lt;positive_integer>]]) | (-XMLWSIURL &lt;expression>  [-XMLWSIChecks &lt;string>]) | (-XMLValidationURL &lt;expression>  (-XMLRequestSchema &lt;string> | (-XMLWSDL &lt;string>  [-XMLAdditionalSOAPHeaders ( ON | OFF )]  [-XMLEndPointCheck ( ABSOLUTE | RELATIVE )]) | -XMLValidateSOAPEnvelope ( ON | OFF ))  [-XMLResponseSchema &lt;string>]    [-XMLValidateResponse ( ON | OFF )]) | (-XMLAttachmentURL &lt;expression>  [-XMLMaxAttachmentSizeCheck ( ON | OFF )  [-XMLMaxAttachmentSize &lt;positive_integer>]]  [-XMLAttachmentContentTypeCheck ( ON | OFF )  [-XMLAttachmentContentType &lt;expression>]]) | (-XMLSQLInjection &lt;string>  [-isRegex ( REGEX | NOTREGEX )]  [-location ( ELEMENT | ATTRIBUTE )]) | (-XMLXSS &lt;string>  [-isRegex ( REGEX | NOTREGEX )]  [-location ( ELEMENT | ATTRIBUTE )]) | -contentType &lt;expression> | -excludeResContentType &lt;expression> | (-CreditCardNumber &lt;expression>  &lt;CreditCardNumberUrl>)) [-comment &lt;string>] [-state ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name of the profile to which to bind an exemption or rule.

<b>startURL</b>
Add the specified URL to the start URL list. 
Enclose URLs in double quotes to ensure preservation of any embedded spaces or non-alphanumeric characters.

<b>denyURL</b>
Add the specified URL to the deny URL list. 
Enclose URLs in double quotes to ensure preservation of any embedded spaces or non-alphanumeric characters.

<b>fieldConsistency</b>
Exempt the specified web form field and form action URL from the form field consistency check, or exempt the specified cookie from the cookie consistency check.  
A form field consistency exemption (relaxation) consists of the following items:
* Web form field name. Name of the form field to exempt from this check.
* Form action URL. Action URL for the web form.
* IsRegex flag. The IsRegex flag, followed by YES if the form action URL is a regular expression, or NO if it is a literal string.

<b>formActionURL</b>
Form action URL.

<b>isRegex</b>
Is a regular expression?
Possible values: REGEX, NOTREGEX

<b>cookieConsistency</b>
A cookie consistency exemption (relaxation) consists of the following items:
* Cookie name. Name of the cookie to exempt from this check.
* IsRegex flag. The IsRegex flag, followed by YES if the cookie name is a regular expression, or NO if it is a literal string.

<b>SQLInjection</b>
Exempt the specified HTTP header, web form field and the form action URL, or cookie from the SQL injection check.  
An SQL injection exemption (relaxation) consists of the following items:
*Item name. Name of the web form field, cookie, or HTTP header to exempt from this check.
* Form action URL. If the item to be exempted is a web form field, the action URL for the web form.
* IsRegex flag. The IsRegex flag, followed by YES if the name or form action URL is a regular expression, or NO if it is a literal string.
* Location. Location that should be examined by the SQL injection check, either FORMFIELD for web form field, HEADER for HTTP header, or COOKIE for cookie.

<b>location</b>
Location of XSS injection exception - XML Element or Attribute. Default location is 'ELEMENT'
Possible values: ELEMENT, ATTRIBUTE
Default value: AS_XMLLOCATION_ELEMENT

<b>valueType</b>
XSS value type. (Tag | Attribute | Pattern)
Possible values: Tag, Attribute, Pattern

<b>valueExpression</b>
XSS value expressions consistituting expressions for Tag, Attribute and Pattern.

<b>isValueRegex</b>
Is a regular expression?
Possible values: REGEX, NOTREGEX

<b>CSRFTag</b>
Exempt the specified form field and web form from the cross-site request forgery (CSRF tagging) check.
A CSRF tagging exemption (relaxation) consists of the following items:
* Web form field name. Regular expression that describes the web form field to exempt from this check.
* Form action URL. The action URL for the web form.

<b>CSRFFormActionURL</b>
CSRF form action URL.

<b>crossSiteScripting</b>
Exempt the specified string, found in the specified HTTP header, cookie, or web form, from the cross-site scripting check.  
A cross-site scripting check exemption (relaxation) consists of the following items:
* HTML to exempt. The string to exempt from the cross-site scripting check.
* URL. The URL to exempt.
* IsRegex flag. The IsRegex flag, followed by YES if the URL is a regular expression, or NO if it is a literal string.
* location. Location which should be examined by the cross-site scripting check, either FORMFIELD for web form field, HEADER for HTTP header, or COOKIE for cookie.

<b>fieldFormat</b>
Impose the specified format on content returned by users in the specified web form field. 
A field format rule consists of the following items:
* Form field name. The name of the form field.
* Form action URL. The form action URL for the web form.
* Field type. The field type (format) to enforce on the specified web form field.
* Field format minimum length. The minimum length allowed for data in the specified field. If 0, field can be left blank.
* Field format maximum length. The maximum length allowed for data in the specified field.
* IsRegex flag. The IsRegex flag, followed by YES if the URL is a regular expression, or NO if it is a literal string.

<b>fieldType</b>
Field type.

<b>fieldFormatMinLength</b>
Field format minimum length.
Default value: 0 
Minimum value: 0
Maximum value: 65535

<b>fieldFormatMaxLength</b>
Field format maximum length.
Default value: 65535 
Minimum value: 1
Maximum value: 65535

<b>safeObject</b>
Protect web sites from exposing sensitive private information such as social security numbers, credit card numbers, driver's license numbers, passport numbers, and any other type of private information that can be described by a regular expression.
A safe object consists of the following items:
* Name. A name that describes the type of information that the safe object is to protect. 
* Expression. PCRE-format regular expression that describes the information to be protected.
* Maximum match length. Maximum length of a matched string.
* Action. "X-Out" to mask blocked information with the letter X, or "Remove" to remove the information.

<b>expression</b>
Safe Object regular expression.

<b>maxMatchLength</b>
Maximum match length for a Safe Object expression.
Default value: 1
Minimum value: 1
Maximum value: 65535

<b>action</b>
Safe Object action types. (BLOCK | LEARN | LOG | STATS | NONE)

<b>trustedLearningClients</b>
Trusted host/network learning IP.
This binding is appilicable to profile Type: HTML, XML.

<b>comment</b>
Any comments about the purpose of profile, or other useful information about the profile.

<b>state</b>
Enabled.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>XMLDoSURL</b>
Exempt the specified URL from the specified XML denial-of-service (XDoS) attack protections.
An XDoS exemption (relaxation) consists of the following items:
* URL. PCRE-format regular expression for the URL or URLs to be exempted.
* Maximum-element-depth-check toggle.  ON to enable this check, OFF to disable it.
* Maximum-element-depth-check toggle.  ON to enable, OFF to disable.
* Maximum-element-depth-check level. Positive integer representing the maximum allowed depth of nested XML elements.
* Maximum-element-name-length-check toggle. ON to enable, OFF to disable.
 * Maximum element name length. Positive integer representing the maximum allowed length of XML element names.
* Maximum-number-of-elements-check toggle. ON to enable, OFF to disable.
* Maximum number of elements. Positive integer representing the maximum allowed number of XML elements.
* Maximum-number-of-element-children-check toggle. ON to enable, OFF to disable.
* Maximum number of element children. Positive integer representing the maximum allowed number of XML element children.
* Maximum-number-of-attributes-check toggle. ON to enable, OFF to disable.
* Maximum number of attributes. Positive integer representing the maximum allowed number of XML attributes.
* Maximum-attribute-name-length-check toggle. ON to enable, OFF to disable.
* Maximum attribute name length. Positive integer representing the maximum allowed length of XML attribute names.
* Maximum-attribute-value-length-check toggle. ON to enable, OFF to disable.
* Maximum attribute value length. Positive integer representing the maximum allowed length of XML attribute values.
* Maximum-character-data-length-check toggle. ON to enable, OFF to disable.
 * Maximum character-data length. Positive integer representing the maximum allowed length of XML character data.
* Maximum-file-size-check toggle. ON to enable, OFF to disable.
 * Maximum file size. Positive integer representing the maximum allowed size, in bytes. of attached or uploaded files.
* Minimum-file-size-check toggle. ON to enable, OFF to disable.
* Minimum file size. Positive integer representing the minimum allowed size, in bytes, of attached or uploaded files.
* Maximum-number-of-entity-expansions-check toggle. ON to enable, OFF to disable.
* Maximum number of entity expansions. Positive integer representing the maximum allowed number of XML entity expansions.
* Maximum-number-of XML-namespaces-check toggle. ON to enable, OFF to disable.
* Maximum number of XML namespaces. Positive integer representing the maximum allowed number of XML namespaces.
* Maximum-XML-namespace-URI-length-check toggle. ON to enable, OFF to disable.
* MaximumXML-namespace URI length. Positive integer representing the maximum allowed length of XML namespace URIs.
* Block-processing-instructions toggle. Block XML processing instructions. ON to enable, OFF to disable.
* Block-DTD toggle. Block design type documents (DTDs). ON to enable, OFF to disable.
* Block-external-XML-entitites toggle. ON to enable, OFF to disable.
* Maximum-SOAP-array-check toggle. ON to enable, OFF to disable.
* Maximum SOAP-array size. Positive integer representing the maximum allowed size of XML SOAP arrays.
* Maximum SOAP-array rank. Positive integer representing the maximum rank (dimensions) of any single XML SOAP array.

<b>XMLMaxElementDepthCheck</b>
State if XML Max Element Depth Check is ON or OFF.
Possible values: ON, OFF
Default value: OFF

<b>XMLMaxElementDepth</b>
Maximum nesting (depth) of XML elements. This check protects against documents that have excessive depth of hierarchy.
Default value: 256
Minimum value: 1
Maximum value: 65535

<b>XMLMaxElementNameLengthCheck</b>
State if XML Max Element Name Length Check is ON or OFF.
Possible values: ON, OFF
Default value: OFF

<b>XMLMaxElementNameLength</b>
Specify the longest name of any element (including the prefix for qualified element name) to protect against overflow attacks.
Default value: 128
Minimum value: 1
Maximum value: 65535

<b>XMLMaxElementsCheck</b>
State if XML Max Elements Check is ON or OFF.
Possible values: ON, OFF
Default value: OFF

<b>XMLMaxElements</b>
Specifying maximum number of elements protects against overflow attacks.
Default value: 65535
Minimum value: 1
Maximum value: 65535

<b>XMLMaxElementChildrenCheck</b>
State if XML Max Element Children Check is ON or OFF.
Possible values: ON, OFF
Default value: OFF

<b>XMLMaxElementChildren</b>
Specifying maximum number of children allowed per element protects against overflow attacks.
Default value: 65535
Minimum value: 0
Maximum value: 65535

<b>XMLMaxAttributesCheck</b>
State if XML Max Attributes Check is ON or OFF.
Possible values: ON, OFF
Default value: OFF

<b>XMLMaxAttributes</b>
Specify maximum number of attributes per element. Protects against overflow attacks.
Default value: 256
Minimum value: 0
Maximum value: 65535

<b>XMLMaxAttributeNameLengthCheck</b>
State if XML Max Attribute Name Length Check is ON or OFF.
Possible values: ON, OFF
Default value: OFF

<b>XMLMaxAttributeNameLength</b>
Specify the longest name of any attribute (including the prefix for qualified attribute name). Protects against overflow attacks.
Default value: 128
Minimum value: 1
Maximum value: 65535

<b>XMLMaxAttributeValueLengthCheck</b>
State if XML Max Atribute Value Length is ON or OFF.
Possible values: ON, OFF
Default value: OFF

<b>XMLMaxAttributeValueLength</b>
Specify the longest value of any attribute. Protects against overflow attacks.
Default value: 2048
Minimum value: 0
Maximum value: 65535

<b>XMLMaxCharDATALengthCheck</b>
State if XML Max CDATA Length Check is ON or OFF.
Possible values: ON, OFF
Default value: OFF

<b>XMLMaxCharDATALength</b>
Maximum size of CDATA protects against overflow attacks and large unparsed data within XML messages.
Default value: 65535
Minimum value: 0
Maximum value: 1000000000

<b>XMLMaxFileSizeCheck</b>
State if XML Max File Size Check is ON or OFF.
Possible values: ON, OFF
Default value: OFF

<b>XMLMaxFileSize</b>
Maximum size of the XML messages protects against overflow attacks.
Default value: 20000000 
Minimum value: 4
Maximum value: 1000000000

<b>XMLMinFileSizeCheck</b>
State if XML Min File Size Check is ON or OFF.
Possible values: ON, OFF
Default value: OFF

<b>XMLMinFileSize</b>
Enforces minimum message size.
Default value: 9
Minimum value: 4
Maximum value: 1000000000

<b>XMLBlockPI</b>
State if XML Block PI is ON or OFF. Protects resources from denial of service attacks as SOAP messages can not have Processing Instruction (PI) in the message.
Possible values: ON, OFF
Default value: OFF

<b>XMLBlockDTD</b>
State if XML DTD is ON or OFF. Protects against recursive Document Type Declaration (DTD) entity expansion attacks. Also, SOAP messages can not have DTD in the message. 
Possible values: ON, OFF
Default value: OFF

<b>XMLBlockExternalEntities</b>
State if XML Block External Entities Check is ON or OFF. Protects against XML External Entity (XXE) attacks that force applications to parse untrusted external entities (sources) in XML documents.
Possible values: ON, OFF
Default value: OFF

<b>XMLMaxEntityExpansionsCheck</b>
State if XML Max Entity Expansions Check is ON or OFF.
Possible values: ON, OFF
Default value: OFF

<b>XMLMaxEntityExpansions</b>
Specify maximum allowed number of entity expansions. Protects aganist Entity Expansion Attack.
Default value: 512
Minimum value: 0
Maximum value: 1024

<b>XMLMaxEntityExpansionDepthCheck</b>
State if XML Max Entity Expansions Depth Check is ON or OFF.
Possible values: ON, OFF
Default value: OFF

<b>XMLMaxEntityExpansionDepth</b>
Specify maximum entity expansion depth. Protects aganist Entity Expansion Attack.
Default value: 8
Minimum value: 0
Maximum value: 24

<b>XMLMaxNamespacesCheck</b>
State if XML Max Namespaces Check is ON or OFF.
Possible values: ON, OFF
Default value: OFF

<b>XMLMaxNamespaces</b>
Specify maximum number of active namespaces. Protects against overflow attacks.
Default value: 16
Minimum value: 0
Maximum value: 512

<b>XMLMaxNamespaceUriLengthCheck</b>
State if XML Max Namspace URI Length Check is ON or OFF.
Possible values: ON, OFF
Default value: OFF

<b>XMLMaxNamespaceUriLength</b>
Specify the longest URI of any XML namespace. Protects against overflow attacks.
Default value: 256
Minimum value: 0
Maximum value: 65535

<b>XMLSOAPArrayCheck</b>
State if XML SOAP Array check is ON or OFF.
Possible values: ON, OFF
Default value: OFF

<b>XMLMaxSOAPArraySize</b>
XML Max Total SOAP Array Size. Protects against SOAP Array Abuse attack.
Default value: 20000000 
Minimum value: 0
Maximum value: 1000000000

<b>XMLMaxSOAPArrayRank</b>
XML Max Total SOAP Array Rank. Protects against SOAP Array Abuse attack.
Default value: 16
Minimum value: 0
Maximum value: 32

<b>XMLWSIURL</b>
Exempt the specified URL from the web services interoperability (WS-I) check. The URL is specified as a PCRE-format regular expression, which can match one or more URLs.

<b>XMLWSIChecks</b>
Synonym for XMLWISURL, but takes a literal URL instead of a PCRE-format regular expression.

<b>XMLValidationURL</b>
Exempt the specified URL from the XML message validation check.
An XML message validation exemption (relaxation) consists of the following items:
* URL. PCRE-format regular expression that matches the URL(s) to be exempted.
* XML-request-schema toggle. Use the specified XML schema to validate requests. ON to enable, OFF to disable.
* XML request schema. XML schema to use for validating requests.
* XML-response-schema toggle. Use the specified XML schema to validate responses. ON to enable, OFF to disable.
* XML response schema. XML schema to use for validating responses.
* WSDL toggle. Use the specified WSDL to validate. ON to enable, OFF to disable.
* WSDL. WSDL to use for validation.
* SOAP-envelope toggle. Validate against the SOAP envelope. ON to enable, OFF to disable.
* Additional-SOAP-headers toggle. Validate against the extended list of SOAP headers. ON to enable, OFF to disable.
* XML-end-point check. ABSOLUTE to use an absolute end point, RELATIVE to use a relative end point.

<b>XMLRequestSchema</b>
XML Schema object for request validation .

<b>XMLResponseSchema</b>
XML Schema object for response validation .

<b>XMLWSDL</b>
WSDL object for soap request validation .

<b>XMLAdditionalSOAPHeaders</b>
Allow addtional soap headers.
Possible values: ON, OFF

<b>XMLEndPointCheck</b>
Modifies the behaviour of the Request URL validation w.r.t. the Service URL.
	If set to ABSOLUTE, the entire request URL is validated with the entire URL mentioned in Service of the associated WSDL.
		eg: Service URL: http://example.org/ExampleService, Request URL: http//example.com/ExampleService would FAIL the validation.
	If set to RELATIVE, only the non-hostname part of the request URL is validated against the non-hostname part of the Service URL.
		eg: Service URL: http://example.org/ExampleService, Request URL: http//example.com/ExampleService would PASS the validation.
Possible values: ABSOLUTE, RELATIVE
Default value: ABSOLUTE

<b>XMLValidateSOAPEnvelope</b>
Validate SOAP Evelope only.
Possible values: ON, OFF

<b>XMLValidateResponse</b>
Validate response message.
Possible values: ON, OFF

<b>XMLAttachmentURL</b>
Exempt the specified URL from the XML attachment check. 
An XML attachment exemption (relaxation) consists of the following items:
* URL. PCRE-format regular expression that matches the URL(s) to be exempted.
* Maximum-attachment-size-check toggle. ON to enable, OFF to disable.
* Maximum attachment size. Positive integer representing the maximum allowed size in bytes for each XML attachment.
* Attachment-content-type-check toggle. ON to enable, OFF to disable.
* Attachment content type. PCRE-format regular expression that specifies the list of MIME content types allowed for XML attachments.

<b>XMLMaxAttachmentSizeCheck</b>
State if XML max attachment size check is ON or OFF. Protects against XML requests with large attachment data.
Possible values: ON, OFF
Default value: OFF

<b>XMLMaxAttachmentSize</b>
Specify maximum attachment size.
Minimum value: 0
Maximum value: 1000000000

<b>XMLAttachmentContentTypeCheck</b>
State if XML attachment content-type check is ON or OFF. Protects against XML requests with illegal attachments.
Possible values: ON, OFF
Default value: OFF

<b>XMLAttachmentContentType</b>
Specify content-type regular expression.

<b>XMLSQLInjection</b>
Exempt the specified URL from the XML SQL injection check. 
An XML SQL injection exemption (relaxation) consists of the following items:
* URL. URL to exempt, as a string or a PCRE-format regular expression.
* ISREGEX flag. REGEX if URL is a regular expression, NOTREGEX if URL is a fixed string.
* Location. ELEMENT if the injection is located in an XML element, ATTRIBUTE if located in an XML attribute.

<b>XMLXSS</b>
Exempt the specified URL from the XML cross-site scripting (XSS) check.
An XML cross-site scripting exemption (relaxation) consists of the following items:
* URL. URL to exempt, as a string or a PCRE-format regular expression.
* ISREGEX flag. REGEX if URL is a regular expression, NOTREGEX if URL is a fixed string.
* Location. ELEMENT if the attachment is located in an XML element, ATTRIBUTE if located in an XML attribute.

<b>contentType</b>
Add the specified content-type to the content-type list.Enclose content-type in double quotes to ensure preservation of any embedded spaces or non-alphanumeric characters.

<b>excludeResContentType</b>
Add the specified content-type to the response content-type list that are to be excluded from inspection. Enclose content-type in double quotes to ensure preservation 
of any embedded spaces or non-alphanumeric characters.

<b>CreditCardNumber</b>
Add expression to the list of object expression which are to be bypassed from safe commerce checks.

<b>CreditCardNumberUrl</b>
The url for which the list of credit card numbers are needed to be bypassed from inspection



##unbind appfw profile

Unbinds the specified exemption (relaxation) or rule from the specified application firewall profile. See the bind appfw profile command for a description of the parameters.


##Synopsys

unbind appfw profile &lt;name> (-startURL &lt;expression> | -denyURL &lt;expression> | (-fieldConsistency &lt;string>  &lt;formActionURL>) | -cookieConsistency &lt;string> | (-SQLInjection &lt;string>  &lt;formActionURL>  [-location &lt;location>]  [-valueType &lt;valueType>  [&lt;valueExpression>]]) | (-CSRFTag &lt;string>  &lt;CSRFFormActionURL>) | (-crossSiteScripting &lt;string>  &lt;formActionURL>  [-location &lt;location>]  [-valueType &lt;valueType>  [&lt;valueExpression>]]) | (-fieldFormat &lt;string>  &lt;formActionURL>) | -safeObject &lt;string> | -trustedLearningClients &lt;ip_addr[/prefix]|ipv6_addr[/prefix]|*> | -XMLDoSURL &lt;expression> | -XMLWSIURL &lt;expression> | -XMLValidationURL &lt;expression> | -XMLAttachmentURL &lt;expression> | (-XMLSQLInjection &lt;string>  [-location ( ELEMENT | ATTRIBUTE )]) | (-XMLXSS &lt;string>  [-location ( ELEMENT | ATTRIBUTE )]) | -contentType &lt;expression> | -excludeResContentType &lt;expression> | (-CreditCardNumber &lt;expression>  &lt;CreditCardNumberUrl>))


##Arguments

<b>name</b>
Name of the exemption (relaxation) or rule that you want to unbind.

<b>startURL</b>
Start URL regular expression.

<b>denyURL</b>
Deny URL regular expression.

<b>fieldConsistency</b>
Form field name.

<b>formActionURL</b>
Form action URL.

<b>cookieConsistency</b>
Cookie name.

<b>SQLInjection</b>
Form field, header or cookie name.

<b>location</b>
Location of XSS injection exception - XML Element or Attribute. Default location is 'ELEMENT'
Possible values: ELEMENT, ATTRIBUTE
Default value: AS_XMLLOCATION_ELEMENT

<b>valueType</b>
The web form value type.
Possible values: Tag, Attribute, Pattern

<b>valueExpression</b>
The web form value expression.

<b>CSRFTag</b>
CSRF Form origin URL.
This binding is applicable to Profile Type: HTML.

<b>CSRFFormActionURL</b>
CSRF form action URL.

<b>crossSiteScripting</b>
Form field, header or cookie name.

<b>fieldFormat</b>
Field format name.

<b>safeObject</b>
Safe Object name.

<b>trustedLearningClients</b>
Trusted learning Clients IP

<b>XMLDoSURL</b>
XML DoS URL regular expression.

<b>XMLWSIURL</b>
XML WS-I URL regular expression.

<b>XMLValidationURL</b>
XML Message URL regular expression.

<b>XMLAttachmentURL</b>
XML Attachment URL regular expression.

<b>XMLSQLInjection</b>
Exempt the specified URL from the XML SQL injection check. 
An XML SQL injection exemption (relaxation) consists of the following items:
* URL. URL to exempt, as a string or a PCRE-format regular expression.
* ISREGEX flag. REGEX if URL is a regular expression, NOTREGEX if URL is a fixed string.
* Location. ELEMENT if the injection is located in an XML element, ATTRIBUTE if located in an XML attribute.

<b>XMLXSS</b>
Exempt the specified URL from the XML cross-site scripting (XSS) check.
An XML cross-site scripting exemption (relaxation) consists of the following items:
* URL. URL to exempt, as a string or a PCRE-format regular expression.
* ISREGEX flag. REGEX if URL is a regular expression, NOTREGEX if URL is a fixed string.
* Location. ELEMENT if the attachment is located in an XML element, ATTRIBUTE if located in an XML attribute.

<b>contentType</b>
content-type  regular expression.

<b>excludeResContentType</b>
Response content type regular expression that are to be excluded from inspection.

<b>CreditCardNumber</b>
The object expression that is to be excluded from safe commerce check.

<b>CreditCardNumberUrl</b>
The url for which the list of credit card numbers are needed to be bypassed from inspection



##show appfw profile

Displays details of the specified application firewall profile. If no profile is specified, displays a list of all application firewall profiles on the NetScaler appliance.


##Synopsys

show appfw profile [&lt;name>]


##Arguments

<b>name</b>
Name of the application firewall profile.



##Outputs

<b>stateflag</b>

<b>type</b>
The profile type of of this Application Firewall profile. If the profile is of the HTML type, only checks relevant to HTML are applied. If the profile is of the XML type, only checks relevent to XML are applied.  if the profile is of the Web 2.0 type, then both types of checks are applied.

<b>defaults</b>
Default configuration to apply to the profile. Basic defaults are intended for standard content that requires little further configuration, such as static web site content. Advanced defaults are intended for specialized content that requires significant specialized configuration, such as heavily scripted or dynamic content.
CLI users: When adding an application firewall profile, you can set either the defaults or the type, but not both. To set both options, create the profile by using the add appfw profile command, and then use the set appfw profile command to configure the other option.

<b>useHTMLErrorObject</b>
Send an imported HTML Error object to a user when a request is blocked, instead of redirecting the user to the designated Error URL.

<b>errorURL</b>
The error page for this profile.

<b>HTMLErrorObject</b>
Name to assign to the HTML Error Object. 
Must begin with a letter, number, or the underscore character \\(_\\), and must contain only letters, numbers, and the hyphen \\(-\\), period \\(.\\) pound \\(\\#\\), space \\( \\), at (@), equals \\(=\\), colon \\(:\\), and underscore characters. Cannot be changed after the HTML error object is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks \\(for example, "my HTML error object" or 'my HTML error object'\\).

<b>logEveryPolicyHit</b>
Log every profile match, regardless of security checks results.

<b>stripComments</b>
Tells the Application Firewall to strip HTML comments from responses before sending them to the user.

<b>stripHtmlComments</b>
Tells the Application Firewall to strip HTML comments from responses before sending them to the user.

<b>stripXmlComments</b>
Tells the Application Firewall to strip XML comments from responses before sending them to the user.

<b>defaultCharSet</b>
The default character set.  The character set that the Application Firewall uses for web pages that do not explicitly set a different character set.

<b>postBodyLimit</b>
The maximum body size for an HTTP POST.

<b>fileUploadMaxNum</b>
Maximum allowed number of file uploads per form-submission request. The maximum setting (65535) allows an unlimited number of uploads.

<b>canonicalizeHTMLResponse</b>
Tells the Application Firewall to convert any non-ASCII characters into HTML entities before sending responses to the user. This is called 'canonicalization' of HTML responses.

<b>enableFormTagging</b>
Enables tagging of web forms for form field Consistency checks.

<b>sessionlessFieldConsistency</b>
Enable session less form field consistency checks.

<b>sessionlessURLClosure</b>
Enable session less URL closure checks.

<b>semicolonFieldSeparator</b>
Allow ';' as a form field separator in URL queries and POST form bodies.

<b>excludeFileUploadFromChecks</b>
Excludes uploaded files from all web form checks.

<b>SQLInjectionParseComments</b>
Canonicalizes SQL Comments in form fields.

<b>checkRequestHeaders</b>
Check request headers as well as web forms for injected SQL and cross-site scripts.

<b>optimizePartialReqs</b>
Optimize handle of HTTP partial requests i.e. those with range headers.
Available settings are as follows: 
* ON  - Partial requests by the client result in partial requests to the backend server in most cases.
* OFF - Partial requests by the client are changed to full requests to the backend server

<b>URLDecodeRequestCookies</b>
URL Decode request cookies before subjecting them to SQL and cross-site scripting checks.

<b>comment</b>
Comments associated with this profile.

<b>startURLAction</b>
Start URL action types. (BLOCK | LEARN | LOG | STATS | NONE)

<b>contentTypeAction</b>
Content-type action types. (BLOCK | LOG | NONE)

<b>inspectContentTypes</b>
Inspection content types associated with this profile

<b>startURL</b>
A regular expression that designates a URL on the Start URL list.

<b>startURLClosure</b>
Enable Start URL closure. When enabled, this feature allows users to start their session at a designated start URL, then navigate from that start URL to any URL on a protected web site by clicking a link on another web page on that web site.  Otherwise, requests to any URL that is not explicitly allowed are blocked.

<b>denyURLAction</b>
Deny URL action types. (BLOCK | LOG | STATS | NONE)

<b>denyURL</b>
A regular expression that designates a URL on the Deny URL list.

<b>RefererHeaderCheck</b>
Enable validation of Referer headers. 
Referer validation ensures that a web form that a user sends to your web site originally came from your web site, not an outside attacker. 
Although this parameter is part of the Start URL check, referer validation protects against cross-site request forgery (CSRF) attacks, not Start URL attacks.

<b>CSRFtagAction</b>
Cross-site request forgery tagging action types. (BLOCK | LEARN | LOG | STATS | NONE)

<b>CSRFTag</b>
The web form originating URL.

<b>CSRFFormActionURL</b>
The web form action URL.

<b>crossSiteScriptingAction</b>
Cross-site scripting action types. (BLOCK | LEARN | LOG | STATS | NONE)

<b>crossSiteScriptingTransformUnsafeHTML</b>
Enables transformation of unsafe HTML into safe HTML before forwarding a request to the web server.

<b>crossSiteScriptingCheckCompleteURLs</b>
Tells the Application Firewall to check complete URLs rather than just the query portion of URLs for cross-site scripting violations.

<b>crossSiteScripting</b>
The web form field name.

<b>isRegex</b>
Is the XML XSS exempted field name a regular expression?

<b>formActionURL</b>
Action URL of the form field to which a field format will be assigned.

<b>exemptClosureURLsFromSecurityChecks</b>
Tells the Application Firewall to exempt closure URLs from security checks.

<b>location</b>
Location of XSS injection exception - XML Element or Attribute.

<b>valueType</b>
The web form value type.

<b>valueExpression</b>
The web form value expression.

<b>isValueRegex</b>
Is the web form field value a regular expression?

<b>SQLInjectionAction</b>
SQL injection action types. (BLOCK | LEARN | LOG | STATS | NONE)

<b>SQLInjectionTransformSpecialChars</b>
Enables transformation of SQL special characters found in web forms into safe equivalents.

<b>SQLInjectionOnlyCheckFieldsWithSQLChars</b>
Tells the Application Firewall to check form fields that contain SQL special characters only, rather than all form fields, for SQL injection violations.

<b>SQLInjectionType</b>
Available SQL Injection types.

<b>SQLInjectionCheckSQLWildChars</b>
Check for form fields that contain SQL wild chars .

<b>SQLInjection</b>
The web form field name.

<b>invalidPercentHandling</b>
Configure the method that the application firewall uses to handle percent-encoded names and values. Available settings function as follows: 
* apache_mode - Apache format.
* asp_mode - Microsoft ASP format.
* secure_mode - Secure format.

<b>fieldConsistencyAction</b>
Form Field Consistency action types. (BLOCK | LEARN | LOG | STATS | NONE)

<b>fieldConsistency</b>
The web form field name.

<b>cookieConsistencyAction</b>
Cookie consistency action types. (BLOCK | LEARN | LOG | STATS | NONE)

<b>cookieConsistency</b>
The name of the cookie to be checked.

<b>cookieTransforms</b>
Perform the specified type of cookie transformation. 
Available settings function as follows: 
* Encryption - Encrypt cookies.
* Proxying - Mask contents of server cookies by sending proxy cookie to users.
* Cookie flags - Flag cookies as HTTP only to prevent scripts on user's browser from accessing and possibly modifying them.
CAUTION: Make sure that this parameter is set to ON if you are configuring any cookie transformations. If it is set to OFF, no cookie transformations are performed regardless of any other settings.

<b>cookieEncryption</b>
Type of cookie encryption. Available settings function as follows:
* None - Do not encrypt cookies.
* Decrypt Only - Decrypt encrypted cookies, but do not encrypt cookies.
* Encrypt Session Only - Encrypt session cookies, but not permanent cookies.
* Encrypt All - Encrypt all cookies.

<b>cookieProxying</b>
Proxies server cookies using the Application Firewall session

<b>addCookieFlags</b>
Add the specified flags to cookies. Available settings function as follows:
* None - Do not add flags to cookies.
* HTTP Only - Add the HTTP Only flag to cookies, which prevents scripts from accessing cookies.
* Secure - Add Secure flag to cookies.
* All - Add both HTTPOnly and Secure flags to cookies.

<b>bufferOverflowAction</b>
Buffer overflow action types. (BLOCK | LOG | STATS | NONE)

<b>bufferOverflowMaxURLLength</b>
Maximum allowed length for URLs.

<b>bufferOverflowMaxHeaderLength</b>
Maximum allowed length for HTTP headers.

<b>bufferOverflowMaxCookieLength</b>
Maximum allowed length for cookies.

<b>fieldFormatAction</b>
Field format action types. (BLOCK | LEARN | LOG | STATS | NONE)

<b>defaultFieldFormatType</b>
Name of the default field type, the field type that the Application Firewall will assign to a form field when no specific field type is assigned to that particular form field.

<b>defaultFieldFormatMinLength</b>
Default field type minimum length setting.

<b>defaultFieldFormatMaxLength</b>
Default field type maximum length setting.

<b>fieldFormat</b>
Name of the form field to which a field format will be assigned.

<b>fieldType</b>
The field type you are assigning to this form field.

<b>fieldFormatMinLength</b>
The minimum allowed length for data in this form field.

<b>fieldFormatMaxLength</b>
The maximum allowed length for data in this form field.

<b>creditCardAction</b>
Credit Card action types. (BLOCK | LOG | STATS | NONE)

<b>creditCard</b>
Credit card types. (AMEX | DINERSCLUB| DISCOVER | JBC | MASTERCARD | VISA)

<b>creditCardMaxAllowed</b>
Maximum number of times a credit card number may be seen before action is taken.

<b>creditCardXOut</b>
X-out credit card numbers.

<b>doSecureCreditCardLogging</b>
Setting this option logs credit card numbers in the response when the match is found.

<b>streaming</b>
Setting this option converts content-length form submission requests (requests with content-type "application/x-www-form-urlencoded" or "multipart/form-data") to chunked requests when atleast one of the following protections : SQL injection protection, XSS protection, form field consistency protection, starturl closure, CSRF tagging is enabled. Please make sure that the backend server accepts chunked requests before enabling this option.

<b>trace</b>
Toggle  the state of trace

<b>safeObject</b>
Name of the Safe Object.

<b>expression</b>
A regular expression that defines the Safe Object.

<b>maxMatchLength</b>
Maximum match length for a Safe Object expression.

<b>action</b>
Safe Object action types. (BLOCK | LOG | STATS | NONE)

<b>requestContentType</b>
Default content-type for request messages.

<b>responseContentType</b>
Default content-type for response messages.

<b>XMLErrorObject</b>
URL for the xml error page

<b>signatures</b>
Signatures for the profile

<b>XMLFormatAction</b>
XML well-formed request action types. (BLOCK | LOG | STATS | NONE)

<b>XMLDoSAction</b>
XML DOS action types. (BLOCK | LEARN | LOG | STATS | NONE)

<b>XMLSQLInjectionAction</b>
XML SQL Injection action types. (BLOCK | LOG | STATS | NONE)

<b>XMLSQLInjectionOnlyCheckFieldsWithSQLChars</b>
XML flag to check only fields with SQL characters.

<b>XMLSQLInjectionType</b>
Available XML SQL Injection types.

<b>XMLSQLInjectionCheckSQLWildChars</b>
XML flag to check for SQL wild chars.

<b>XMLSQLInjectionParseComments</b>
Canonicalize SQL Comments in XML data.

<b>XMLXSSAction</b>
XML cross-site scripting action types. (BLOCK | LOG | STATS | NONE)

<b>XMLWSIAction</b>
XML WSI action types. (BLOCK | LEARN | LOG | STATS | NONE)

<b>XMLAttachmentAction</b>
XML attachment action types. (BLOCK | LEARN | LOG | STATS | NONE)

<b>XMLValidationAction</b>
XML message validation action types. (BLOCK | LOG | STATS | NONE)

<b>XMLSOAPFaultAction</b>
XML SOAP fault filtering action types. (BLOCK | LOG | STATS | REMOVE | NONE)

<b>XMLDoSURL</b>
XML DoS URL regular expression length.

<b>XMLWSIURL</b>
XML WS-I URL regular expression length.

<b>XMLValidationURL</b>
XML Validation URL regular expression.

<b>XMLAttachmentURL</b>
XML attachment URL regular expression length.

<b>XMLSQLInjection</b>
Exempt the specified URL from the XML SQL injection check. 
An XML SQL injection exemption (relaxation) consists of the following items:
* URL. URL to exempt, as a string or a PCRE-format regular expression.
* ISREGEX flag. REGEX if URL is a regular expression, NOTREGEX if URL is a fixed string.
* Location. ELEMENT if the injection is located in an XML element, ATTRIBUTE if located in an XML attribute.

<b>XMLXSS</b>
Exempt the specified URL from the XML cross-site scripting (XSS) check.
An XML cross-site scripting exemption (relaxation) consists of the following items:
* URL. URL to exempt, as a string or a PCRE-format regular expression.
* ISREGEX flag. REGEX if URL is a regular expression, NOTREGEX if URL is a fixed string.
* Location. ELEMENT if the attachment is located in an XML element, ATTRIBUTE if located in an XML attribute.

<b>state</b>
Enabled.

<b>XMLMaxElementDepthCheck</b>
State if XML Max element depth check is ON or OFF.

<b>XMLMaxElementDepth</b>
Maximum nesting (depth) of XML elements. This check protects against documents that have excessive hierarchy depths.

<b>XMLMaxElementNameLengthCheck</b>
State if XML Max element name length check is ON or OFF.

<b>XMLMaxElementNameLength</b>
Specify the longest name of any element (including the expanded namespace) to protect against overflow attacks.

<b>XMLMaxElementsCheck</b>
State if XML Max elements check is ON or OFF.

<b>XMLMaxElements</b>
Specify the maximum number of XML elements allowed. Protects against overflow attacks.

<b>XMLMaxElementChildrenCheck</b>
State if XML Max element children check is ON or OFF.

<b>XMLMaxElementChildren</b>
Specify the maximum number of children allowed per XML element. Protects against overflow attacks.

<b>XMLMaxNodesCheck</b>
State if XML Max nodes check is ON or OFF.

<b>XMLMaxNodes</b>
Specify the maximum number of XML nodes. Protects against overflow attacks.

<b>XMLMaxAttributesCheck</b>
State if XML Max attributes check is ON or OFF.

<b>XMLMaxAttributes</b>
Specify maximum number of attributes per XML element. Protects against overflow attacks.

<b>XMLMaxAttributeNameLengthCheck</b>
State if XML Max attribute name length check is ON or OFF.

<b>XMLMaxAttributeNameLength</b>
Specify the longest name of any XML attribute. Protects against overflow attacks.

<b>XMLMaxAttributeValueLengthCheck</b>
State if XML Max atribute value length is ON or OFF.

<b>XMLMaxAttributeValueLength</b>
Specify the longest value of any XML attribute. Protects against overflow attacks.

<b>XMLMaxCharDATALengthCheck</b>
State if XML Max CDATA length check is ON or OFF.

<b>XMLMaxCharDATALength</b>
Specify the maximum size of CDATA. Protects against overflow attacks and large quantities of unparsed data within XML messages.

<b>XMLMaxFileSizeCheck</b>
State if XML Max file size check is ON or OFF.

<b>XMLMaxFileSize</b>
Specify the maximum size of XML messages. Protects against overflow attacks.

<b>XMLMinFileSizeCheck</b>
State if XML Min file size check is ON or OFF.

<b>XMLMinFileSize</b>
Enforces minimum message size.

<b>XMLBlockPI</b>
State if XML Block PI is ON or OFF. Protects resources from denial of service attacks as SOAP messages cannot have processing instructions (PI) in messages.

<b>XMLBlockDTD</b>
State if XML DTD is ON or OFF. Protects against recursive Document Type Declaration (DTD) entity expansion attacks. Also, SOAP messages cannot have DTDs in messages.

<b>XMLBlockExternalEntities</b>
State if XML Block External Entities Check is ON or OFF. Protects against XML External Entity (XXE) attacks that force applications to parse untrusted external entities (sources) in XML documents.

<b>XMLMaxEntityExpansionsCheck</b>
State if XML Max Entity Expansions Check is ON or OFF.

<b>XMLMaxEntityExpansions</b>
Specify maximum allowed number of entity expansions. Protects aganist Entity Expansion Attack.

<b>XMLMaxEntityExpansionDepthCheck</b>
State if XML Max Entity Expansions Depth Check is ON or OFF.

<b>XMLMaxEntityExpansionDepth</b>
Specify maximum entity expansion depth. Protects aganist Entity Expansion Attack.

<b>XMLMaxNamespacesCheck</b>
State if XML Max namespaces check is ON or OFF.

<b>XMLMaxNamespaces</b>
Specify maximum number of active namespaces. Protects against overflow attacks.

<b>XMLMaxNamespaceUriLengthCheck</b>
State if XML Max namespace URI length check is ON or OFF.

<b>XMLMaxNamespaceUriLength</b>
Specify the longest URI of any XML namespace. Protects against overflow attacks.

<b>XMLSOAPArrayCheck</b>
State if XML SOAP Array check is ON or OFF.

<b>XMLMaxSOAPArraySize</b>
XML Max Total SOAP Array Size. Protects against SOAP Array Abuse attack.

<b>XMLMaxSOAPArrayRank</b>
XML Max Individual SOAP Array Rank. This is the dimension of the SOAP array.

<b>XMLWSIChecks</b>
Specify a comma separated list of relevant WS-I rule IDs. (R1140, R1141)

<b>XMLRequestSchema</b>
XML Schema object for request validation .

<b>XMLResponseSchema</b>
XML Schema object for response validation.

<b>XMLWSDL</b>
WSDL object for soap request validation.

<b>XMLAdditionalSOAPHeaders</b>
Allow addtional soap headers.

<b>XMLEndPointCheck</b>
Modifies the behaviour of the Request URL validation w.r.t. the Service URL.
	If set to ABSOLUTE, the entire request URL is validated with the entire URL mentioned in Service of the associated WSDL.
		eg: Service URL: http://example.org/ExampleService, Request URL: http//example.com/ExampleService would FAIL the validation.
	If set to RELAIVE, only the non-hostname part of the request URL is validated against the non-hostname part of the Service URL.
		eg: Service URL: http://example.org/ExampleService, Request URL: http//example.com/ExampleService would PASS the validation.

<b>XMLValidateSOAPEnvelope</b>
Validate SOAP Evelope only.

<b>XMLValidateResponse</b>
Validate response message.

<b>XMLMaxAttachmentSizeCheck</b>
State if XML Max attachment size Check is ON or OFF. Protects against XML requests with large attachment data.

<b>XMLMaxAttachmentSize</b>
Specify maximum attachment size.

<b>XMLAttachmentContentTypeCheck</b>
State if XML attachment content-type check is ON or OFF. Protects against XML requests with illegal attachments.

<b>XMLAttachmentContentType</b>
Specify content-type regular expression.

<b>builtin</b>
Indicates that a profile is a built-in entity.

<b>builtinType</b>
Type of built-in profiles

<b>trustedLearningClients</b>
Specify trusted host/network IP

<b>contentType</b>
A regular expression that designates a content-type on the content-types list.

<b>excludeResContentType</b>
A regular expression that represents the content type of the response that are to be excluded from inspection.

<b>CreditCardNumber</b>
The object expression that is to be excluded from safe commerce check

<b>CreditCardNumberUrl</b>
The url for which the list of credit card numbers are needed to be bypassed from inspection

<b>devno</b>

<b>count</b>



##stat appfw profile

Displays statistics for the specified application firewall profile. If no profile is specified, displays abbreviated statistics for all profiles.


##Synopsys

stat appfw profile [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
Name of the application firewall profile.

<b>detail</b>
Specifies detailed output (including more statistics). The output can be quite voluminous. Without this argument, the output will show only a summary.

<b>fullValues</b>
Specifies that numbers and strings should be displayed in their full form. Without this option, long strings are shortened and large numbers are abbreviated

<b>ntimes</b>
The number of times, in intervals of seven seconds, the statistics should be displayed.
Default value: 1
Minimum value: 0

<b>logFile</b>
The name of the log file to be used as input.

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>requests (reqs)</b>
HTTP/HTTPS requests sent to your protected web servers via the Application Firewall.

<b>Request Bytes (reqBytes)</b>
Number of bytes transfered for requests

<b>responses (resps)</b>
HTTP/HTTPS responses sent by your protected web servers via the Application Firewall.

<b>Response Bytes (resBytes)</b>
Number of bytes transfered for responses

<b>aborts</b>
Incomplete HTTP/HTTPS requests aborted by the client before the Application Firewall could finish processing them.

<b>redirects (redirect)</b>
HTTP/HTTPS requests redirected by the Application Firewall to a different Web page or web server. (HTTP 302)

<b>Long Term Ave Response Time (ms) (longAvgRespTimePP)</b>
Average backend response time in milliseconds since reboot

<b>Recent Ave Response Time (ms) (shortAvgRespTimePP)</b>
Average backend response time in milliseconds over the last 7 seconds

<b>start URL (startURL)</b>
Number of Start URL security check violations seen by the Application Firewall.

<b>deny URL (denyURL)</b>
Number of Deny URL security check violations seen by the Application Firewall.

<b>referer header (refererHdr)</b>
Number of Referer Header security check violations seen by the Application Firewall.

<b>buffer overflow (bufovfl)</b>
Number of Buffer Overflow security check violations seen by the Application Firewall.

<b>cookie consistency (cookie)</b>
Number of Cookie Consistency security check violations seen by the Application Firewall.

<b>CSRF form tag (csrf_tag)</b>
Number of Cross Site Request Forgery form tag security check violations seen by the Application Firewall.

<b>HTML Cross-site scripting (xss)</b>
Number of HTML Cross-Site Scripting security check violations seen by the Application Firewall.

<b>HTML SQL injection (sql)</b>
Number of HTML SQL Injection security check violations seen by the Application Firewall.

<b>field format (fieldfmt)</b>
Number of Field Format security check violations seen by the Application Firewall.

<b>field consistency (fieldcon)</b>
Number of Field Consistency security check violations seen by the Application Firewall.

<b>credit card (ccard)</b>
Number of Credit Card security check violations seen by the Application Firewall.

<b>safe object (safeobj)</b>
Number of Safe Object security check violations seen by the Application Firewall.

<b>Signature Violations (sigs)</b>
Number of Signature violations seen by the Application Firewall.

<b>content Type (contentType)</b>
Number of Content Type security check violations seen by the Application Firewall.

<b>XML Format (wfcViolations)</b>
Number of XML Format security check violations seen by the Application Firewall.

<b>XML Denial of Service (XDoS) (xdosViolations)</b>
Number of XML Denial-of-Service security check violations seen by the Application Firewall.

<b>XML Message Validation (msgvalViolations)</b>
Number of XML Message Validation security check violations seen by the Application Firewall.

<b>Web Services Interoperability (wsIViolations)</b>
Number of Web Services Interoperability (WS-I) security check violations seen by the Application Firewall.

<b>XML SQL Injection (xmlSqlViolations)</b>
Number of XML SQL Injection security check violations seen by the Application Firewall.

<b>XML Cross-Site Scripting (xmlXssViolations)</b>
Number of XML Cross-Site Scripting (XSS) security check violations seen by the Application Firewall.

<b>XML Attachment (xmlAttachmentViolations)</b>
Number of XML Attachment security check violations seen by the Application Firewall.

<b>SOAP Fault Violations (soapflt)</b>
Number of requests returning soap:fault from the backend server

<b>XML Generic Violations (genflt)</b>
Number of requests returning XML generic violation from the backend server

<b>Total Violations (totperpr)</b>
Number of violations seen by the application firewall on per profile basis

<b>start URL logs (startURLLog)</b>
Number of Start URL security check log messages generated by the Application Firewall.

<b>deny URL logs (denyURLLog)</b>
Number of Deny URL security check log messages generated by the Application Firewall.

<b>referer header logs (refererHdrLog)</b>
Number of Referer Header security check log messages generated by the Application Firewall.

<b>buffer overflow logs (bufovflLog)</b>
Number of Buffer Overflow security check log messages generated by the Application Firewall.

<b>cookie consistency logs (cookieLog)</b>
Number of Cookie Consistency security check log messages generated by the Application Firewall.

<b>CSRF form tag logs (csrf_tagLog)</b>
Number of Cross Site Request Forgery form tag security check log messages generated by the Application Firewall.

<b>HTML XSS logs (xssLog)</b>
Number of HTML Cross-Site Scripting security check log messages generated by the Application Firewall.

<b>HTML XSS transform logs (xssXformLog)</b>
Number of HTML Cross-Site Scripting security check transform log messages generated by the Application Firewall.

<b>HTML SQL Injection logs (sqlLog)</b>
Number of HTML SQL Injection security check log messages generated by the Application Firewall.

<b>HTML SQL transform logs (sqlXformLog)</b>
Number of HTML SQL Injection security check transform log messages generated by the Application Firewall.

<b>field format logs (fieldfmtLog)</b>
Number of Field Format security check log messages generated by the Application Firewall.

<b>field consistency logs (fieldconLog)</b>
Number of Field Consistency security check log messages generated by the Application Firewall.

<b>credit cards (ccardLog)</b>
Number of Credit Card security check log messages generated by the Application Firewall.

<b>credit card transform logs (ccardXformLog)</b>
Number of Credit Card security check transform log messages generated by the Application Firewall.

<b>safe object logs (safeobjLog)</b>
Number of Safe Object security check log messages generated by the Application Firewall.

<b>Signature logs (sigs)</b>
Number of Signature log messages generated by the Application Firewall.

<b>content Type logs (contenttypeLog)</b>
Number of Content type security check log messages generated by the Application Firewall.

<b>XML Format logs (wfcLogs)</b>
Number of XML Format security check log messages generated by the Application Firewall.

<b>XML Denial of Service(XDoS) logs (xdosLogs)</b>
Number of XML Denial-of-Service security check log messages generated by the Application Firewall.

<b>XML Message Validation logs (msgvalLogs)</b>
Number of XML Message Validation security check log messages generated by the Application Firewall.

<b>WSI logs (wsILogs)</b>
Number of Web Services Interoperability (WS-I) security check log messages generated by the Application Firewall.

<b>XML SQL Injection logs (xmlSqlLogs)</b>
Number of XML SQL Injection security check log messages generated by the Application Firewall.

<b>XML XSS logs (xmlXssLogs)</b>
Number of XML Cross-Site Scripting (XSS) security check log messages generated by the Application Firewall.

<b>XML Attachment logs (xmlAttachmentLogs)</b>
Number of XML Attachment security check log messages generated by the Application Firewall.

<b>SOAP Fault logs (soapfltLogs)</b>
Number of requests generating soap:fault log messages

<b>XML Generic logs (genfltLog)</b>
Number of requests generating XML Generic log messages

<b>Total log messages (totlogperpr)</b>
Number of log messages generated by the application firewall on per profile basis

<b>HTTP Client Errors (4xx Resp) (4xxResps)</b>
Number of requests returning HTTP 4xx from the backend server

<b>HTTP Server Errors (5xx Resp) (5xxResps)</b>
Number of requests returning HTTP 5xx from the backend server



##Example

stat appfw profile

##Related Commands

<ul><li><a href="../../..//">stat appfw</a></li><li><a href="../../../stat-appfw-p/stat-appfw-p">stat appfw policy</a></li><li><a href="../../../html#stat-appfw-policy/html#stat-appfw-policy">stat appfw policylabel</a></li></ul>



##archive appfw profile

Create archive for the profile.


##Synopsys

archive appfw profile &lt;name> &lt;archivename> [-comment &lt;string>]


##Arguments

<b>name</b>
Name for the profile. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.), pound (#), space ( ), at (@), equals (=), colon (:), and underscore (_) characters. Cannot be changed after the profile is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my profile" or 'my profile').

<b>archivename</b>
Source for tar archive.

<b>comment</b>
Any comments about the purpose of profile, or other useful information about the profile.



##Related Commands

<ul><li><a href="../../../#export-appfw-ar/#export-appfw-ar">export appfw archive</a></li><li><a href="../../../#import-appfw-ar/#import-appfw-ar">import appfw archive</a></li></ul>



##restore appfw profile

Restore configuration from archive file


##Synopsys

restore appfw profile &lt;archivename>


##Arguments

<b>archivename</b>
Source for tar archive.



##Related Commands

<ul><li><a href="../../../#export-appfw-ar/#export-appfw-ar">export appfw archive</a></li><li><a href="../../../#import-appfw-ar/#import-appfw-ar">import appfw archive</a></li></ul>



