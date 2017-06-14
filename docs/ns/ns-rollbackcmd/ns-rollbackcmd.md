#ns rollbackcmd

The following operations can be performed on "ns rollbackcmd":


##show ns rollbackcmd

Generates the command(s) that can be used to roll back the command(s) that are specified in an input file.For example, if you want to roll back the creation of a load balancing virtual server named vserver_test, you must include the 'add lb vserver vserver_test ..' command in the input file. The output of this command is the 'rm lb vserver vserver_test' command.


##Synopsys

show ns rollbackcmd [-fileName &lt;input_filename>] [-outtype ( cli | xml )]


##Arguments

<b>fileName</b>
File that contains the commands for which the rollback commands must be generated. Specify the full path of the file name.

<b>outtype</b>
Format in which the rollback commands must be generated.
Possible values: cli, xml



##Example

show ns rollbackcmd -file &lt;file_name&gt;

