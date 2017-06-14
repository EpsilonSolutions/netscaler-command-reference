#cli attribute

The following operations can be performed on "cli attribute":


##show cli attribute

Display attributes of the NetScaler CLI


##Synopsys

show cli attribute


##Outputs

<b>qquote</b>
The construct that is used to quote strings that are to be taken as-is, without interpreting escape sequences like "
".
This construct consists of: a 'q', followed by a delimiter character; the string follows immediately after the delimiter and is terminated by the first matching delimiter character. (The set of possible delimiter characters is listed below.)
For example, q/a
/ will result in a three-character string ('a', '', 'n'); whereas "a
" results in a two-character string ('a' followed by a newline).

<b>qquoteDelimiters</b>
The set of characters that can be used as the delimiter in a q// construct.  Characters shown in pairs must be used that way, whereas characters shown singly server as thier own matching delimiter.
For example, q?abc? and q{abc} are valid q// constructs, and evaluate to the string "abc"; q{abc{ is however not a valid q// construct so it will evaluate to the string "q{abc{".



