#policy stringmap

The following operations can be performed on "policy stringmap":


[add](#add-policy-stringmap) | [rm](#rm-policy-stringmap) | [set](#set-policy-stringmap) | [unset](#unset-policy-stringmap) | [bind](#bind-policy-stringmap) | [unbind](#unbind-policy-stringmap) | [show](#show-policy-stringmap)

##add policy stringmap

Creates a string map. You must use the 'bind policy stringmap' command to bind strings to this string map.


##Synopsys

add policy stringmap &lt;name> [-comment &lt;string>]


##Arguments

<b>name</b>
Unique name for the string map. Not case sensitive. Must begin with an ASCII letter or underscore (_) character, and must consist only of ASCII alphanumeric or underscore characters. Must not begin with 're' or 'xp' or be a word reserved for use as a default syntax expression qualifier prefix (such as HTTP) or enumeration value (such as ASCII). Must not be the name of an existing named expression, pattern set, dataset, string map, or HTTP callout.

<b>comment</b>
Comments associated with the string map.



##Example

i)	add stringmap custom_stringmap.	This creates a new string map with name custom_stringmap.

##rm policy stringmap

Removes a string map. String maps can be removed only if not used in any part of policy, action, or expression.


##Synopsys

rm policy stringmap &lt;name>


##Arguments

<b>name</b>
Name of the string map to remove.



##Example

i)	rm stringmap custom_stringmap.	This removes a string map whose name is custom_stringmap

##set policy stringmap

Modifies the attributes of an existing string map.


##Synopsys

set policy stringmap &lt;name> -comment &lt;string>


##Arguments

<b>name</b>
Name of the string map to be modified.

<b>comment</b>
Comments associated with the string map.



##Example

i)	set stringmap custom_stringmap -comment "custom string map is for URLs.".	This updates the comment associated with the string map whose name is custom_stringmap

##unset policy stringmap

Use this command to remove policy stringmap settings.Refer to the set policy stringmap command for meanings of the arguments.


##Synopsys

unset policy stringmap &lt;name> -comment


##bind policy stringmap

Binds a key and its associated value to a string map. If the key already exists and has a different value, the old value is overwritten with the new value.


##Synopsys

bind policy stringmap &lt;name> &lt;key> &lt;value>


##Arguments

<b>name</b>
Name of the string map to which to bind the key-value pair.

<b>key</b>
Character string constituting the key to be bound to the string map. The key is matched against the data processed by the operation that uses the string map. The default character set is ASCII. UTF-8 characters can be included if the character set is UTF-8.  UTF-8 characters can be entered directly (if the UI supports it) or can be encoded as a sequence of hexadecimal bytes '\\xNN'. For example, the UTF-8 character '?' can be encoded as '\\xC3\\xBC'.

<b>value</b>
Character string constituting the value associated with the key. This value is returned when processed data matches the associated key. Refer to the key parameter for details of the value character set.



##Example

bind stringmap custom_stringmap "key-string" "value-string".	This adds the key "key-string" and its associated value "value-string" to the string map whose name is custom_stringmap.

##unbind policy stringmap

Removes a key from the string map.


##Synopsys

unbind policy stringmap &lt;name> &lt;key>


##Arguments

<b>name</b>
Name of the string map from which to remove a key.

<b>key</b>
Key to remove from the string map.



##Example

unbind stringmap custom_stringmap key1.	This removes the key "key1" and its associated value from the string map whose name is custom_stringmap.

##show policy stringmap

Displays a list of available string maps.


##Synopsys

show policy stringmap [&lt;name>]


##Arguments

<b>name</b>
Name of the string map to display. If a name is not provided, a list of all the configured string maps is shown.



##Outputs

<b>stateflag</b>

<b>comment</b>
Comments associated with the string map.

<b>key</b>
Character string constituting the key to be bound to the string map. The key is matched against the data processed by the operation that uses the string map. The default character set is ASCII. UTF-8 characters can be included if the character set is UTF-8.  UTF-8 characters can be entered directly (if the UI supports it) or can be encoded as a sequence of hexadecimal bytes '\\xNN'. For example, the UTF-8 character '?' can be encoded as '\\xC3\\xBC'.

<b>value</b>
Character string constituting the value associated with the key. This value is returned when processed data matches the associated key. Refer to the key parameter for details of the value character set.

<b>devno</b>

<b>count</b>



##Example

show stringmap custom_stringmap. Displays all the key-value pairs of a string map whose name is custom-stringmap

