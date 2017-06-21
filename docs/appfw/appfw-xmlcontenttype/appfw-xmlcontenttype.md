#appfw XMLContentType

The following operations can be performed on "appfw XMLContentType":


[add](#add-appfw-xmlcontenttype) | [rm](#rm-appfw-xmlcontenttype) | [show](#show-appfw-xmlcontenttype)

##add appfw XMLContentType

Add XML content type. This will classify a request/response with the specified content type as XML


##Synopsys

add appfw XMLContentType &lt;XMLContenttypevalue> [-isRegex ( REGEX | NOTREGEX )]


##Arguments

<b>XMLContenttypevalue</b>
Content type to be classified as XML

<b>isRegex</b>
Is field name a regular expression?
Possible values: REGEX, NOTREGEX
Default value: NOTREGEX



##rm appfw XMLContentType

Remove XML content type.


##Synopsys

rm appfw XMLContentType &lt;XMLContenttypevalue>


##Arguments

<b>XMLContenttypevalue</b>
Content type to be classified as XML



##show appfw XMLContentType

Display all xml content types.


##Synopsys

show appfw XMLContentType [&lt;XMLContenttypevalue>]


##Arguments

<b>XMLContenttypevalue</b>
Content type to be classified as XML



##Outputs

<b>isRegex</b>
Is field name a regular expression?

<b>builtin</b>
Flag to determine if xmlcontenttype is built-in or not

<b>devno</b>

<b>count</b>

<b>stateflag</b>



