#stream selector

The following operations can be performed on "stream selector":


[add](#add-stream-selector) | [set](#set-stream-selector) | [rm](#rm-stream-selector) | [show](#show-stream-selector)

##add stream selector

Creates a selector for Action Analytics or traffic rate limiting.


##Synopsys

add stream selector &lt;name> &lt;rule> ...


##Arguments

<b>name</b>
Name for the selector. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. If the name includes one or more spaces, and you are using the NetScaler CLI, enclose the name in double or single quotation marks (for example, "my selector" or 'my selector').

<b>rule</b>
Set of up to five individual (not compound) default syntax expressions. Maximum length: 7499 characters. Each expression must identify a specific request characteristic, such as the client's IP address (with CLIENT.IP.SRC) or requested server resource (with HTTP.REQ.URL). 
Note: If two or more selectors contain the same expressions in different order, a separate set of records is created for each selector.



##Example

add stream selector sel_subnet HTTP.REQ.URL CLIENT.IP.SRC.SUBNET(24)

##set stream selector

Modifies the set of expressions in a stream selector. Note: You can change an expression if the selector is not yet being used in an identifier. If the selector is already in use, you can change only the order of the expressions, not the expressions themselves.


##Synopsys

set stream selector &lt;name> -rule &lt;expression> ...


##Arguments

<b>name</b>
Name of the selector for which to modify parameters.

<b>rule</b>
Set of up to five individual (not compound) default syntax expressions. Maximum length: 7499 characters. Each expression must identify a specific request characteristic, such as the client's IP address (with CLIENT.IP.SRC) or requested server resource (with HTTP.REQ.URL). 
Note: If two or more selectors contain the same expressions in different order, a separate set of records is created for each selector.



##Example

set stream sel_subnet HTTP.REQ.URL CLIENT.IP.SRC

##rm stream selector

Removes a selector. Note: Before you remove a selector, make sure that it is not being used by an identifier.


##Synopsys

rm stream selector &lt;name>


##Arguments

<b>name</b>
Name for the selector. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. If the name includes one or more spaces, and you are using the NetScaler CLI, enclose the name in double or single quotation marks (for example, "my selector" or 'my selector').



##Example

rm stream selector sel_subnet

##show stream selector

Displays the expressions configured for the specified selector or, if no selector name is specified, the expressions configured for all selectors.


##Synopsys

show stream selector [&lt;name>]


##Arguments

<b>name</b>
Name for the selector. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. If the name includes one or more spaces, and you are using the NetScaler CLI, enclose the name in double or single quotation marks (for example, "my selector" or 'my selector').

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>rule</b>
Set of up to five individual (not compound) default syntax expressions. Maximum length: 7499 characters. Each expression must identify a specific request characteristic, such as the client's IP address (with CLIENT.IP.SRC) or requested server resource (with HTTP.REQ.URL). 
Note: If two or more selectors contain the same expressions in different order, a separate set of records is created for each selector.

<b>builtin</b>
Flag to determine if stream selector is built-in or not

<b>stateflag</b>

<b>devno</b>

<b>count</b>



##Example

show ns limitSelector sel_subnet

