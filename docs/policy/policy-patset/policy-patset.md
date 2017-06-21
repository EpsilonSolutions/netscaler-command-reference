#policy patset

The following operations can be performed on "policy patset":


[add](#add-policy-patset) | [rm](#rm-policy-patset) | [bind](#bind-policy-patset) | [unbind](#unbind-policy-patset) | [show](#show-policy-patset)

##add policy patset

Adds a pattern set. A pattern set contains a name and one or more string patterns. Pattern sets can be used in default syntax expressions to match a set of strings. For example, HTTP.REQ.URL.EQUALS_ANY("test_urls"), where test_urls is a pattern set containing URL strings. Pattern sets can also be used in the search parameter of a rewrite action. Each string pattern is assigned an index that enables you to select the associated string from the set.


##Synopsys

add policy patset &lt;name> [-comment &lt;string>]


##Arguments

<b>name</b>
Unique name of the pattern set. Not case sensitive. Must begin with an ASCII letter or underscore (_) character and must contain only alphanumeric and underscore characters. Must not be the name of an existing named expression, pattern set, dataset, string map, or HTTP callout.

<b>comment</b>
Any comments to preserve information about this patset.



##Example

add policy patset pat1

##rm policy patset

Removes a pattern set. If the pattern set is used by an expression in another object, such as a policy, you must remove the object before removing the pattern set.


##Synopsys

rm policy patset &lt;name>


##Arguments

<b>name</b>
Name of the pattern set to remove.



##Example

rm policy patset pat1

##bind policy patset

Binds a string to a pattern set.


##Synopsys

bind policy patset &lt;name> &lt;string> [-index &lt;positive_integer>] [-charset ( ASCII | UTF_8 )]


##Arguments

<b>name</b>
Name of the pattern set to which to bind the string.

<b>string</b>
String of characters that constitutes a pattern. For more information about the characters that can be used, refer to the character set parameter.
Note: Minimum length for pattern sets used in rewrite actions of type REPLACE_ALL, DELETE_ALL, INSERT_AFTER_ALL, and INSERT_BEFORE_ALL, is three characters.

<b>index</b>
Integer that identifies the string pattern within the pattern set. You can assign index values or allow them to be assigned automatically. If you specify an index for the first pattern that you bind to the set, you must do so for each subsequent pattern. If you do not specify an index for the first pattern, the NetScaler generates an index. If you subsequently specify an index when binding a pattern to the set, an error message appears.
The pattern index of a matching pattern can be used within default syntax expressions. For example, HTTP.REQ.URL.EQUALS_INDEX("test_url").EQ(5), returns true if the request URL matches the strings in the test_url pattern set with index 5.
Minimum value: 1
Maximum value: 4294967290

<b>charset</b>
Character set associated with the characters in the string.
Note: UTF-8 characters can be entered directly (if the UI supports it) or can be encoded as a sequence of hexadecimal bytes '\\xNN'. For example, the UTF-8 character '?' can be encoded as '\\xC3\\xBC'.
Possible values: ASCII, UTF_8



##Example

bind policy patset pat1 bar -index 2

##unbind policy patset

Unbinds a string from a pattern set.


##Synopsys

unbind policy patset &lt;name> &lt;string> ...


##Arguments

<b>name</b>
Name of the pattern set from which to unbind a string.

<b>string</b>
String of characters to unbind from the pattern set.



##Example

unbind policy patset pat1 bar xyz

##show policy patset

Displays the list of pattern sets configured on the appliance.


##Synopsys

show policy patset [&lt;name>]


##Arguments

<b>name</b>
Name of the pattern set for which to display the detailed information. If a name is not provided, a list of all pattern sets configured on the appliance is shown.



##Outputs

<b>stateflag</b>

<b>string</b>
String of characters that constitutes a pattern. For more information about the characters that can be used, refer to the character set parameter.
Note: Minimum length for pattern sets used in rewrite actions of type REPLACE_ALL, DELETE_ALL, INSERT_AFTER_ALL, and INSERT_BEFORE_ALL, is three characters.

<b>index</b>
The index of the string associated with the patset.

<b>charset</b>
Character set associated with the characters in the string.
Note: UTF-8 characters can be entered directly (if the UI supports it) or can be encoded as a sequence of hexadecimal bytes '\\xNN'. For example, the UTF-8 character '?' can be encoded as '\\xC3\\xBC'.

<b>description</b>
Description of the patset

<b>isDefault</b>

<b>indexType</b>
Index type.

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.

<b>MaxIndex</b>
Maximum number of patterns bounded to pattern set. The maxindex value will not be decreased when we unbind a pattern from the patset. This field is used in auto-generated indexing type.

<b>comment</b>
Any comments to preserve information about this patset.

<b>devno</b>

<b>count</b>



##Example

show policy patset pat1

