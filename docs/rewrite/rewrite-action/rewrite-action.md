#rewrite action

The following operations can be performed on "rewrite action":


[add](#add-rewrite-action) | [rm](#rm-rewrite-action) | [set](#set-rewrite-action) | [unset](#unset-rewrite-action) | [show](#show-rewrite-action) | [rename](#rename-rewrite-action)

##add rewrite action

Creates a rewrite action, which specifies exactly what modifications to make to a request or response before forwarding that request or response to the protected web server or to the user.In addition to user-defined actions, the rewrite feature has the following three built-in actions:* NOREWRITE - Sends the request or response to the user without rewriting it.* RESET - Resets the connection and notifies the user?s browser, so that the user can resend the request.* DROP - Drops the connection without sending a response to the user.One of the following three flow types is implicitly associated with every action:* Request - Action applies to the request.* Response - Action applies to the response.* Neutral - Action applies to both requests and responses.


##Synopsys

add rewrite action &lt;name> &lt;type> &lt;target> [&lt;stringBuilderExpr>] [-pattern &lt;expression> | -search &lt;expression>] [-refineSearch &lt;string>] [-comment &lt;string>]


##Arguments

<b>name</b>
Name for the user-defined rewrite action. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Can be changed after the rewrite policy is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my rewrite action" or 'my rewrite action').

<b>type</b>
Type of user-defined rewrite action. The information that you provide for, and the effect of, each type are as follows:: 
* REPLACE &lt;target&gt; &lt;string_builder_expr&gt;. Replaces the string with the string-builder expression.
* REPLACE_ALL &lt;target&gt; &lt;string_builder_expr1&gt; -(pattern|search) &lt;string_builder_expr2&gt;. In the request or response specified by &lt;target&gt;, replaces all occurrences of the string defined by &lt;string_builder_expr1&gt; with the string defined by &lt;string_builder_expr2&gt;. You can use a PCRE-format pattern or the search facility to find the strings to be replaced.
* REPLACE_HTTP_RES &lt;string_builder_expr&gt;. Replaces the complete HTTP response with the string defined by the string-builder expression.
* REPLACE_SIP_RES &lt;target&gt; - Replaces the complete SIP response with the string specified by &lt;target&gt;.
* INSERT_HTTP_HEADER &lt;header_string_builder_expr&gt; &lt;contents_string_builder_expr&gt;. Inserts the HTTP header specified by &lt;header_string_builder_expr&gt; and header contents specified by &lt;contents_string_builder_expr&gt;.
* DELETE_HTTP_HEADER &lt;target&gt;. Deletes the HTTP header specified by &lt;target&gt;.
* CORRUPT_HTTP_HEADER &lt;target&gt;. Replaces the header name of all occurrences of the HTTP header specified by &lt;target&gt; with a corrupted name, so that it will not be recognized by the receiver  Example: MY_HEADER is changed to MHEY_ADER.
* INSERT_BEFORE &lt;string_builder_expr1&gt; &lt;string_builder_expr1&gt;. Finds the string specified in &lt;string_builder_expr1&gt; and inserts the string in &lt;string_builder_expr2&gt; before it.
* INSERT_BEFORE_ALL &lt;target&gt; &lt;string_builder_expr1&gt; -(pattern|search) &lt;string_builder_expr2&gt;. In the request or response specified by &lt;target&gt;, locates all occurrences of the string specified in &lt;string_builder_expr1&gt; and inserts the string specified in &lt;string_builder_expr2&gt; before each. You can use a PCRE-format pattern or the search facility to find the strings.
* INSERT_AFTER &lt;string_builder_expr1&gt; &lt;string_builder_expr2&gt;. Finds the string specified in &lt;string_builder_expr1&gt;, and inserts the string specified in &lt;string_builder_expr2&gt; after it.
* INSERT_AFTER_ALL &lt;target&gt; &lt;string_builder_expr1&gt; -(pattern|search) &lt;string_builder_expr&gt;. In the request or response specified by &lt;target&gt;, locates all occurrences of the string specified by &lt;string_builder_expr1&gt; and inserts the string specified by &lt;string_builder_expr2&gt; after each. You can use a PCRE-format pattern or the search facility to find the strings.
* DELETE &lt;target&gt;. Finds and deletes the specified target.
* DELETE_ALL &lt;target&gt; -(pattern|search) &lt;string_builder_expr&gt;. In the request or response specified by &lt;target&gt;, locates and deletes all occurrences of the string specified by &lt;string_builder_expr&gt;. You can use a PCRE-format pattern or the search facility to find the strings.
* REPLACE_DIAMETER_HEADER_FIELD &lt;target&gt; &lt;field value&gt;. In the request or response modify the header field specified by &lt;target&gt;. Use Diameter.req.flags.SET(&lt;flag&gt;) or Diameter.req.flags.UNSET&lt;flag&gt; as 'stringbuilderexpression' to set or unset flags.
* REPLACE_DNS_HEADER_FIELD &lt;target&gt;. In the request or response modify the header field specified by &lt;target&gt;. 
* REPLACE_DNS_ANSWER_SECTION &lt;target&gt;. Replace the DNS answer section in the response. This is currently applicable for A and AAAA records only. Use DNS.NEW_RRSET_A & DNS.NEW_RRSET_AAAA expressions to configure the new answer section 
Possible values: noop, delete, insert_http_header, delete_http_header, corrupt_http_header, insert_before, insert_after, replace, replace_http_res, delete_all, replace_all, insert_before_all, insert_after_all, clientless_vpn_encode, clientless_vpn_encode_all, clientless_vpn_decode, clientless_vpn_decode_all, insert_sip_header, delete_sip_header, corrupt_sip_header, replace_sip_res, replace_diameter_header_field, replace_dns_header_field, replace_dns_answer_section

<b>target</b>
Default syntax expression that specifies which part of the request or response to rewrite.

<b>stringBuilderExpr</b>
Default syntax expression that specifies the content to insert into the request or response at the specified location, or that replaces the specified string.

<b>pattern</b>
Pattern that is used to match multiple strings in the request or response. The pattern may be a string literal (without quotes) or a PCRE-format regular expression with a delimiter that consists of any printable ASCII non-alphanumeric character except for the underscore (_) and space ( ) that is not otherwise used in the expression. Example: re~https?://|HTTPS?://~ The preceding regular expression can use the tilde (~) as the delimiter because that character does not appear in the regular expression itself. Used in the INSERT_BEFORE_ALL, INSERT_AFTER_ALL, REPLACE_ALL, and DELETE_ALL action types.

<b>search</b>
Search facility that is used to match multiple strings in the request or response. Used in the INSERT_BEFORE_ALL, INSERT_AFTER_ALL, REPLACE_ALL, and DELETE_ALL action types. The following search types are supported:
* Text ("text(string)") - A literal string. Example: -search text("hello")
* Regular expression ("regex(re&lt;delimiter&gt;regular exp&lt;delimiter&gt;)") - Pattern that is used to match multiple strings in the request or response. The pattern may be a string literal (without quotes) or a PCRE-format regular expression with a delimiter that consists of any printable ASCII non-alphanumeric character except for the underscore (_) and space ( ) that is not otherwise used in the expression. Example: -search regex(re~^hello~) The preceding regular expression can use the tilde (~) as the delimiter because that character does not appear in the regular expression itself.
* XPath ("xpath(xp&lt;delimiter&gt;xpath expression&lt;delimiter&gt;)") - An XPath expression. Example: -search xpath(xp%/a/b%)
* JSON ("xpath_json(xp&lt;delimiter&gt;xpath expression&lt;delimiter&gt;)") - An XPath JSON expression. Example: -search xpath_json(xp%/a/b%)
NOTE: JSON searches use the same syntax as XPath searches, but operate on JSON files instead of standard XML files.
* Patset ("patset(patset)") - A predefined pattern set. Example: -search patset("patset1").
* Datset ("dataset(dataset)") - A predefined dataset. Example: -search dataset("dataset1").
* AVP ("avp(avp number)") - AVP number that is used to match multiple AVPs in a Diameter/Radius Message. Example: -search avp(999)

<b>refineSearch</b>
Specify additional criteria to refine the results of the search. 
Always starts with the "extend(m,n)" operation, where 'm' specifies number of bytes to the left of selected data and 'n' specifies number of bytes to the right of selected data.
You can use refineSearch only on body expressions, and for the INSERT_BEFORE_ALL, INSERT_AFTER_ALL, REPLACE_ALL, and DELETE_ALL action types.

<b>comment</b>
Comment. Can be used to preserve information about this rewrite action.



##Example

i)	add rewrite action act_insert INSERT_HTTP_HEADER change_req "\\\\"no change\\\\"".	This Adds to http headerwill add the header change_req: no change.ii)	add rewrite action act_replace REPLACE "HTTP.REQ.URL.PREFIX(1)" "HTTP.REQ.URL.PREFIX(1)+\\\\"citrix/\\\\"".	If HTTP.REQ.URL.PREFIX(1) is / the result would be /citrix/iii)	add rewrite action act_before INSERT_BEFORE "HTTP.REQ.HEADER(\\\\"host\\\\").VALUE(0)" "\\\\"india\\\\"".	If HTTP.REQ.HEADER(\\\\"host\\\\").VALUE(0) is netscaler.com the result would be indianetscaler.comiv)	add rewrite action act_after INSERT_AFTER "HTTP.REQ.HEADER(\\\\"host\\\\").TYPECAST_LIST_T('.').GET(0)" "\\\\"-india\\\\"".	If HTTP.REQ.HEADER(\\\\"host\\\\").VALUE(0) is support.netscaler.com then the result would be support-india.netscaler.comv)	add rewrite action act_delete DELETE "HTTP.REQ.HEADER(\\\\"host\\\\").VALUE(0)"will leave the Host header looking like "HOST: ".vi)	add rewrite action act_delete_header DELETE_HTTP_HEADER Hostwill delete the Host header. If Host header occurs more than once all occurrence of the header will be deleted.vii)	add rewrite action act_corrupt_header CORRUPT_HTTP_HEADER Hostwill corrupt the Host header. If Host header occurs more than once all occurrence of the header will be corrupted.

##rm rewrite action

Removes a rewrite action.


##Synopsys

rm rewrite action &lt;name>


##Arguments

<b>name</b>
Name of the rewrite action to remove.



##Example

rm rewrite action act_before

##set rewrite action

Modifies the specified parameters of a rewrite action.


##Synopsys

set rewrite action &lt;name> [-target &lt;string>] [-stringBuilderExpr &lt;string>] [-pattern &lt;expression> | -search &lt;expression>] [-refineSearch &lt;string>] [-comment &lt;string>]


##Arguments

<b>name</b>
Name of the rewrite action to modify.

<b>target</b>
Expression that specifies which part of the connection to rewrite.

<b>stringBuilderExpr</b>
Default syntax expression that specifies the content to insert into the request or response at the specified location, or that replaces the specified string.

<b>pattern</b>
Pattern that is used to match multiple strings in the request or response. The pattern may be a string literal (without quotes) or a PCRE-format regular expression with a delimiter that consists of any printable ASCII non-alphanumeric character except for the underscore (_) and space ( ) that is not otherwise used in the expression. Example: re~https?://|HTTPS?://~ The preceding regular expression can use the tilde (~) as the delimiter because that character does not appear in the regular expression itself. Used in the INSERT_BEFORE_ALL, INSERT_AFTER_ALL, REPLACE_ALL, and DELETE_ALL action types.

<b>search</b>
Search facility that is used to match multiple strings in the request or response. Used in the INSERT_BEFORE_ALL, INSERT_AFTER_ALL, REPLACE_ALL, and DELETE_ALL action types. The following search types are supported:
* Text ("text(string)") - A literal string. Example: -search text("hello")
* Regular expression ("regex(re&lt;delimiter&gt;regular exp&lt;delimiter&gt;)") - Pattern that is used to match multiple strings in the request or response. The pattern may be a string literal (without quotes) or a PCRE-format regular expression with a delimiter that consists of any printable ASCII non-alphanumeric character except for the underscore (_) and space ( ) that is not otherwise used in the expression. Example: -search regex(re~^hello~) The preceding regular expression can use the tilde (~) as the delimiter because that character does not appear in the regular expression itself.
* XPath ("xpath(xp&lt;delimiter&gt;xpath expression&lt;delimiter&gt;)") - An XPath expression. Example: -search xpath(xp%/a/b%)
* JSON ("xpath_json(xp&lt;delimiter&gt;xpath expression&lt;delimiter&gt;)") - An XPath JSON expression. Example: -search xpath_json(xp%/a/b%)
NOTE: JSON searches use the same syntax as XPath searches, but operate on JSON files instead of standard XML files.
* Patset ("patset(patset)") - A predefined pattern set. Example: -search patset("patset1").
* Datset ("dataset(dataset)") - A predefined dataset. Example: -search dataset("dataset1").
* AVP ("avp(avp number)") - AVP number that is used to match multiple AVPs in a Diameter/Radius Message. Example: -search avp(999)

<b>refineSearch</b>
Specify additional criteria to refine the results of the search. 
Always starts with the "extend(m,n)" operation, where 'm' specifies number of bytes to the left of selected data and 'n' specifies number of bytes to the right of selected data.
You can use refineSearch only on body expressions, and for the INSERT_BEFORE_ALL, INSERT_AFTER_ALL, REPLACE_ALL, and DELETE_ALL action types.

<b>comment</b>
Comment. Can be used to preserve information about this rewrite action.



##Example

set rewrite action rwact1 -target "HTTP.REQ.HEADER(\\\\"MyHdr\\\\")" -stringBuilderExpr "HTTP.REQ.URL.MARK_SAFE"

##unset rewrite action

Use this command to remove rewrite action settings.Refer to the set rewrite action command for meanings of the arguments.


##Synopsys

unset rewrite action &lt;name> [-stringBuilderExpr] [-refineSearch] [-comment]


##show rewrite action

Displays the current settings for the specified rewrite action.If no rewrite action name is provided, displays a list of all rewrite actions currently configured on the NetScaler appliance.


##Synopsys

show rewrite action [&lt;name>]


##Arguments

<b>name</b>
Name of the rewrite action.



##Outputs

<b>stateflag</b>

<b>type</b>
Type of rewrite action. It can be: (delete|replace|insert_http_header|insert_before|insert_after|replace_http_res).

<b>target</b>
Expression specifying which part of HTTP header needs to be rewritten.

<b>stringBuilderExpr</b>
Expression specifying the value of rewritten HTTP header.

<b>pattern</b>
Pattern used for insert_before_all, insert_after_all, replace_all, delete_all action types.

<b>search</b>
Search facility that is used to match multiple strings in the request or response. Used in the INSERT_BEFORE_ALL, INSERT_AFTER_ALL, REPLACE_ALL, and DELETE_ALL action types. The following search types are supported:
* Text ("text(string)") - A literal string. Example: -search text("hello")
* Regular expression ("regex(re&lt;delimiter>regular exp&lt;delimiter>)") - Pattern that is used to match multiple strings in the request or response. The pattern may be a string literal (without quotes) or a PCRE-format regular expression with a delimiter that consists of any printable ASCII non-alphanumeric character except for the underscore (_) and space ( ) that is not otherwise used in the expression. Example: -search regex(re~^hello~) The preceding regular expression can use the tilde (~) as the delimiter because that character does not appear in the regular expression itself.
* XPath ("xpath(xp&lt;delimiter>xpath expression&lt;delimiter>)") - An XPath expression. Example: -search xpath(xp%/a/b%)
* JSON ("xpath_json(xp&lt;delimiter>xpath expression&lt;delimiter>)") - An XPath JSON expression. Example: -search xpath_json(xp%/a/b%)
NOTE: JSON searches use the same syntax as XPath searches, but operate on JSON files instead of standard XML files.
* Patset ("patset(patset)") - A predefined pattern set. Example: -search patset("patset1").
* Datset ("dataset(dataset)") - A predefined dataset. Example: -search dataset("dataset1").
* AVP ("avp(avp number)") - AVP number that is used to match multiple AVPs in a Diameter/Radius Message. Example: -search avp(999)

<b>bypassSafetyCheck</b>
The safety check to allow unsafe expressions.

<b>refineSearch</b>
Specify additional criteria to refine the results of the search. 
Always starts with the "extend(m,n)" operation, where 'm' specifies number of bytes to the left of selected data and 'n' specifies number of bytes to the right of selected data.
You can use refineSearch only on body expressions, and for the INSERT_BEFORE_ALL, INSERT_AFTER_ALL, REPLACE_ALL, and DELETE_ALL action types.

<b>hits</b>
The number of times the action has been taken.

<b>undefHits</b>
The number of times the action resulted in UNDEF.

<b>referenceCount</b>
The number of references to the action.

<b>description</b>
Description of the action

<b>flags</b>

<b>isDefault</b>
A value of true is returned if it is a default rewriteaction.

<b>comment</b>
Comment. Can be used to preserve information about this rewrite action.

<b>builtin</b>
Flag to determine whether rewrite action is built-in or not

<b>devno</b>

<b>count</b>



##Example

1. show rewrite action	2. show rewrite action act_insert

##rename rewrite action

Renames a rewrite action.


##Synopsys

rename rewrite action &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the rewrite action.

<b>newName</b>
New name for the rewrite action. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Can be changed after the rewrite policy is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my rewrite action" or 'my rewrite action').



##Example

rename rewrite action oldname newname

