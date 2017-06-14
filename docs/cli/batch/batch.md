#batch

The following operations can be performed on "batch":


##batch

Use this command to read the contents of a file and execute each line as a separate CLI command. Each command in the file must be on a separate line. Lines starting with # are considered comments.


##Synopsys

batch -fileName &lt;input_filename> [-outfile &lt;output_filename>] [-ntimes &lt;positive_integer>]


##Arguments

<b>fileName</b>
The name of the batch file.

<b>outfile</b>
The name of the file where the executed batch file will write its output. The default is standard output.

<b>ntimes</b>
The number of times the batch file will be executed.
Default value: 1



##Example

batch -f cmds.txt

