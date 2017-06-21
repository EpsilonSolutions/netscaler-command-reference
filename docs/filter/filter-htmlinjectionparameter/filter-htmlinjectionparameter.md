#filter htmlinjectionparameter

The following operations can be performed on "filter htmlinjectionparameter":


[set](#set-filter-htmlinjectionparameter) | [unset](#unset-filter-htmlinjectionparameter) | [show](#show-filter-htmlinjectionparameter)

##set filter htmlinjectionparameter

Sets the HTML injection parameters.


##Synopsys

set filter htmlinjectionparameter [-rate &lt;positive_integer>] [-frequency &lt;positive_integer>] [-strict ( ENABLED | DISABLED )] [-htmlsearchlen &lt;positive_integer>]


##Arguments

<b>rate</b>
For a rate of x, HTML injection is done for 1 out of x policy matches.
Default value: 1
Minimum value: 1

<b>frequency</b>
For a frequency of x, HTML injection is done at least once per x milliseconds.
Default value: 1
Minimum value: 1

<b>strict</b>
Searching for &lt;html&gt; tag. If this parameter is enabled, HTML injection does not insert the prebody or postbody content unless the &lt;html&gt; tag is found.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>htmlsearchlen</b>
Number of characters, in the HTTP body, in which to search for the &lt;html&gt; tag if strict mode is set.
Default value: 1024
Minimum value: 1



##Example

set htmlinjection parameter -rate 10 -frequency 1

##unset filter htmlinjectionparameter

Removes the HTML injection settings..Refer to the set filter htmlinjectionparameter command for meanings of the arguments.


##Synopsys

unset filter htmlinjectionparameter [-rate] [-frequency] [-strict] [-htmlsearchlen]


##Example

	a) unset htmlinjectionparameter -rate	b) unset htmlinjectionparameter -frequency	c) unset htmlinjectionparameter -rate -frequency

##show filter htmlinjectionparameter

Displays the HTML injection parameters.


##Synopsys

show filter htmlinjectionparameter


##Outputs

<b>rate</b>
For a rate of x, HTML injection is done for 1 out of x policy matches.

<b>frequency</b>
For a frequency of x, HTML injection is done at least once per x milliseconds.

<b>strict</b>
Searching for &lt;html> tag. If this parameter is enabled, HTML injection does not insert the prebody or postbody content unless the &lt;html> tag is found.

<b>htmlsearchlen</b>
Number of characters, in the HTTP body, in which to search for the &lt;html> tag if strict mode is set.



##Example

rate	:	10

