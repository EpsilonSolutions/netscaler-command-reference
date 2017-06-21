#cache selector

The following operations can be performed on "cache selector":


[add](#add-cache-selector) | [rm](#rm-cache-selector) | [set](#set-cache-selector) | [show](#show-cache-selector)

##add cache selector

Creates an Integrated Cache selector.  A selector is an abstraction for a collection of PIXL expressions. After creating a selector, you can use it as a hit selector, invalidation selector, or both. You must specify at least one expression when you create a selector.


##Synopsys

add cache selector &lt;selectorName> &lt;rule> ...


##Arguments

<b>selectorName</b>
Name for the selector.  Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.

<b>rule</b>
One or multiple PIXL expressions for evaluating an HTTP request or response.



##rm cache selector

Removes cache selectors. Note: A selector being used as a hit or invalidation selector in any content group cannot be removed without unsetting it from the content group.


##Synopsys

rm cache selector &lt;selectorName>


##Arguments

<b>selectorName</b>
Name of the selector.



##set cache selector

Modify the set of PIXL expressions associated with a cache selector.


##Synopsys

set cache selector &lt;selectorName> &lt;rule> ...


##Arguments

<b>selectorName</b>
Name of the selector to be modified.

<b>rule</b>
One or multiple PIXL expressions for evaluating an HTTP request or response.



##show cache selector

Displays all cache selectors, or the specified.


##Synopsys

show cache selector [&lt;selectorName>]


##Arguments

<b>selectorName</b>
Name of the selector to display.



##Outputs

<b>flags</b>
Flags.

<b>rule</b>
Rule.

<b>builtin</b>

<b>devno</b>

<b>count</b>

<b>stateflag</b>



