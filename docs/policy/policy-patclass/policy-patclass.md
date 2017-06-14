#policy patClass

The following operations can be performed on "policy patClass":


[add](#add-policy-patclass) | [rm](#rm-policy-patclass) | [bind](#bind-policy-patclass) | [unbind](#unbind-policy-patclass) | [show](#show-policy-patclass)

##add policy patClass

Adds a pattern class. Each pattern class is identified by a name. More patterns (strings) can be associated with it later.NOTE: This command is deprecated. This command is deprecated in favor of 'add policy patset'. NOTE: This command is deprecated.This command is deprecated in favor of 'add policy patset'


##Synopsys




##Arguments

<b>name</b>
Name of the pattern class. The name must not exceed 127 characters.

<b>string</b>
String associated with the patclass.



##Example

add policy patclass pat1 foo

##rm policy patClass

Removes a pattern class. Once the pattern class is removed, all the expressions referring it have undefined values.NOTE: This command is deprecated in favor of 'rm policy patset'. NOTE: This command is deprecated.This command is deprecated in favor of 'rm policy patset'


##Synopsys




##Arguments

<b>name</b>
Name of the pattern class.



##Example

rm policy patclass pat1

##bind policy patClass

Binds string(s) to a pattern class.NOTE: This command is deprecated in favor of 'bind policy patset'. NOTE: This command is deprecated.This command is deprecated in favor of 'bind policy patset'


##Synopsys




##Arguments

<b>name</b>
Name of the pattern class.

<b>string</b>
String associated with the patclass.



##Example

bind policy patclass pat1 bar xyz

##unbind policy patClass

Unbinds string(s) from a pattern class.NOTE: This command is deprecated in favor of 'unbind policy patset'. NOTE: This command is deprecated.This command is deprecated in favor of 'unbind policy patset'


##Synopsys




##Arguments

<b>name</b>
Name of the pattern class.

<b>string</b>
String associated with the patclass.



##Example

unbind policy patclass pat1 bar xyz

##show policy patClass

Displays the configured pattern class(es).NOTE: This command is deprecated in favor of 'show policy patset'. NOTE: This command is deprecated.This command is deprecated in favor of 'show policy patset'


##Synopsys




##Arguments

<b>name</b>
Name of the pattern class.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>string</b>
String associated with the patclass.

<b>index</b>
The index of the string associated with the patclass.

<b>charset</b>
The character set of the string associated with patset.

<b>description</b>
Description of the patclass

<b>isDefault</b>

<b>devno</b>

<b>count</b>



##Example

show policy patclass pat1

