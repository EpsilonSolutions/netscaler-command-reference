#ns variable

The following operations can be performed on "ns variable":


[add](#add-ns-variable) | [rm](#rm-ns-variable) | [show](#show-ns-variable)

##add ns variable

Create a variable for use in assignments and default syntax expressions.


##Synopsys

add ns variable &lt;name> -type &lt;string> [-scope global] [-ifFull ( undef | lru )] [-ifValueTooBig ( undef | truncate )] [-ifNoValue ( undef | init )] [-init &lt;string>] [-expires &lt;positive_integer>] [-comment &lt;string>]


##Arguments

<b>name</b>
Variable name.  This follows the same syntax rules as other default syntax expression entity names:
   It must begin with an alpha character (A-Z or a-z) or an underscore (_).
   The rest of the characters must be alpha, numeric (0-9) or underscores.
   It cannot be re or xp (reserved for regular and XPath expressions).
   It cannot be a default syntax expression reserved word (e.g. SYS or HTTP).
   It cannot be used for an existing default syntax expression object (HTTP callout, patset, dataset, stringmap, or named expression).

<b>type</b>
Specification of the variable type; one of the following:
   ulong - singleton variable with an unsigned 64-bit value.
   text(value-max-size) - singleton variable with a text string value.
   map(text(key-max-size),ulong,max-entries) - map of text string keys to unsigned 64-bit values.
   map(text(key-max-size),text(value-max-size),max-entries) - map of text string keys to text string values.
where
   value-max-size is a positive integer that is the maximum number of bytes in a text string value.
   key-max-size is a positive integer that is the maximum number of bytes in a text string key.
   max-entries is a positive integer that is the maximum number of entries in a map variable.
      For a global singleton text variable, value-max-size &lt;= 64000.
      For a global map with ulong values, key-max-size &lt;= 64000.
      For a global map with text values,  key-max-size + value-max-size &lt;= 64000.
   max-entries is a positive integer that is the maximum number of entries in a map variable. This has a theoretical maximum of 2^64-1, but in actual use will be much smaller, considering the memory available for use by the map.
Example:
   map(text(10),text(20),100) specifies a map of text string keys (max size 10 bytes) to text string values (max size 20 bytes), with 100 max entries.

<b>scope</b>
Scope of the variable:
   global - (default) one set of values visible across all Packet Engines and, in a cluster, all nodes
Possible values: global
Default value: NS_VAR_SCOPE_GLOBAL

<b>ifFull</b>
Action to perform if an assignment to a map exceeds its configured max-entries:
   lru - (default) reuse the least recently used entry in the map.
   undef - force the assignment to return an undefined (Undef) result to the policy executing the assignment.
Possible values: undef, lru
Default value: NS_VAR_IF_FULL_LRU

<b>ifValueTooBig</b>
Action to perform if an value is assigned to a text variable that exceeds its configured max-size,
or if a key is used that exceeds its configured max-size:
   truncate - (default) truncate the text string to the first max-size bytes and proceed.
   undef - force the assignment or expression evaluation to return an undefined (Undef) result to the policy executing the assignment or expression.
Possible values: undef, truncate
Default value: NS_VAR_IF_VALUE_TOO_BIG_TRUNCATE

<b>ifNoValue</b>
Action to perform if on a variable reference in an expression if the variable is single-valued and uninitialized
or if the variable is a map and there is no value for the specified key:
   init - (default) initialize the single-value variable, or create a map entry for the key and the initial value,
using the -init value or its default.
   undef - force the expression evaluation to return an undefined (Undef) result to the policy executing the expression.
Possible values: undef, init
Default value: NS_VAR_IF_NO_VALUE_INIT

<b>init</b>
Initialization value for values in this variable. Default: 0 for ulong, NULL for text

<b>expires</b>
Value expiration in seconds. If the value is not referenced within the expiration period it will be deleted. 0 (the default) means no expiration.
Maximum value: 31622400

<b>comment</b>
Comments associated with this variable.



##Example

add ns variable user_privilege_map -type map(text(15),text(10),10000)

##rm ns variable

Remove a variable and its value(s).


##Synopsys

rm ns variable &lt;name>


##Arguments

<b>name</b>
Variable name.  This follows the same syntax rules as other default syntax expression entity names:
   It must begin with an alpha character (A-Z or a-z) or an underscore (_).
   The rest of the characters must be alpha, numeric (0-9) or underscores.
   It cannot be re or xp (reserved for regular and XPath expressions).
   It cannot be a default syntax expression reserved word (e.g. SYS or HTTP).
   It cannot be used for an existing default syntax expression object (HTTP callout, patset, dataset, stringmap, or named expression).



##Example

rm ns variable user_privilege_map

##show ns variable

Display configured variables


##Synopsys

show ns variable [&lt;name>]


##Arguments

<b>name</b>
Variable name.  This follows the same syntax rules as other default syntax expression entity names:
   It must begin with an alpha character (A-Z or a-z) or an underscore (_).
   The rest of the characters must be alpha, numeric (0-9) or underscores.
   It cannot be re or xp (reserved for regular and XPath expressions).
   It cannot be a default syntax expression reserved word (e.g. SYS or HTTP).
   It cannot be used for an existing default syntax expression object (HTTP callout, patset, dataset, stringmap, or named expression).

<b>format</b>

<b>level</b>



##Outputs

<b>type</b>
Specification of the variable type; one of the following:
   ulong - singleton variable with an unsigned 64-bit value.
   text(value-max-size) - singleton variable with a text string value.
   map(text(key-max-size),ulong,max-entries) - map of text string keys to unsigned 64-bit values.
   map(text(key-max-size),text(value-max-size),max-entries) - map of text string keys to text string values.
where
   value-max-size is a positive integer that is the maximum number of bytes in a text string value.
   key-max-size is a positive integer that is the maximum number of bytes in a text string key.
   max-entries is a positive integer that is the maximum number of entries in a map variable.
      For a global singleton text variable, value-max-size &lt;= 64000.
      For a global map with ulong values, key-max-size &lt;= 64000.
      For a global map with text values,  key-max-size + value-max-size &lt;= 64000.
   max-entries is a positive integer that is the maximum number of entries in a map variable. This has a theoretical maximum of 2^64-1, but in actual use will be much smaller, considering the memory available for use by the map.
Example:
   map(text(10),text(20),100) specifies a map of text string keys (max size 10 bytes) to text string values (max size 20 bytes), with 100 max entries.

<b>scope</b>
Scope of the variable:
   global - (default) one set of values visible across all Packet Engines and, in a cluster, all nodes

<b>ifFull</b>
Action to perform if an assignment to a map exceeds its configured max-entries:
   lru - (default) reuse the least recently used entry in the map.
   undef - force the assignment to return an undefined (Undef) result to the policy executing the assignment.

<b>ifValueTooBig</b>
Action to perform if an value is assigned to a text variable that exceeds its configured max-size,
or if a key is used that exceeds its configured max-size:
   truncate - (default) truncate the text string to the first max-size bytes and proceed.
   undef - force the assignment or expression evaluation to return an undefined (Undef) result to the policy executing the assignment or expression.

<b>ifNoValue</b>
Action to perform if on a variable reference in an expression if the variable is single-valued and uninitialized
or if the variable is a map and there is no value for the specified key:
   init - (default) initialize the single-value variable, or create a map entry for the key and the initial value,
using the -init value or its default.
   undef - force the expression evaluation to return an undefined (Undef) result to the policy executing the expression.

<b>expires</b>
Value expiration in seconds. If the value is not referenced within the expiration period it will be deleted. 0 (the default) means no expiration.

<b>init</b>
Initialization value for values in this variable. Default: 0 for ulong, NULL for text

<b>comment</b>
Comments associated with this variable.

<b>builtin</b>
Flag to determine if the variable is built-in or not

<b>referenceCount</b>
The number of references to the variable in expressions and assignments.

<b>stateflag</b>

<b>devno</b>

<b>count</b>



