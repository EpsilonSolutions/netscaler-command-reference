#grep

The following operations can be performed on "grep":


##grep

Searches files or output for lines containing a match to the specified &lt;pattern>.  By default, grep prints the matching lines.


##Synopsys

grep [-c] [-E] [-i] [-v] [-w] [-x] &lt;pattern>


##Arguments

<b>c</b>
Suppress normal output. Instead print a count of matching lines.
With the -v option, count non-matching lines.

<b>E</b>
Interpret &lt;pattern&gt; as an extended regular expression.

<b>i</b>
Ignore case distinctions.

<b>v</b>
Invert the sense of matching, to select non-matching lines.

<b>w</b>
Select only those lines containing matches that form whole words.

<b>x</b>
Select only those matches that exactly match the whole line.

<b>pattern</b>
The pattern (regular expression or text string) for which to search.



##Example

show ns info | grep off -i

