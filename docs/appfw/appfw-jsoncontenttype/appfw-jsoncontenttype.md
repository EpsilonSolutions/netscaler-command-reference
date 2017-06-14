#appfw JSONContentType

The following operations can be performed on "appfw JSONContentType":


[add](#add-appfw-jsoncontenttype) | [rm](#rm-appfw-jsoncontenttype) | [show](#show-appfw-jsoncontenttype)

##add appfw JSONContentType

Add JSON content type. This will classify a request/response with the specified content type as JSON


##Synopsys

add appfw JSONContentType &lt;JSONContenttypevalue> [-isRegex ( REGEX | NOTREGEX )]


##Arguments

<b>JSONContenttypevalue</b>
Content type to be classified as JSON

<b>isRegex</b>
Is json content type a regular expression?
Possible values: REGEX, NOTREGEX
Default value: NS_NOTREGEX



##rm appfw JSONContentType

Remove JSON content type.


##Synopsys

rm appfw JSONContentType &lt;JSONContenttypevalue>


##Arguments

<b>JSONContenttypevalue</b>
Content type to be classified as JSON



##show appfw JSONContentType

Display all JSON content types.


##Synopsys

show appfw JSONContentType [&lt;JSONContenttypevalue>]


##Arguments

<b>JSONContenttypevalue</b>
Content type to be classified as JSON

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>isRegex</b>
Is json content type a regular expression?

<b>builtin</b>
Flag to determine if jsoncontenttype is built-in or not

<b>devno</b>

<b>count</b>

<b>stateflag</b>



