#cli prompt

The following operations can be performed on "cli prompt":


[clear](#clear-cli-prompt) | [set](#set-cli-prompt) | [show](#show-cli-prompt)

##clear cli prompt

Use this command to return the CLI prompt to the default (a single '>').


##Synopsys

clear cli prompt


##set cli prompt

Use this command to customize the CLI prompt.


##Synopsys

set cli prompt &lt;promptString>


##Arguments

<b>promptString</b>
The prompt string.  The following special values are allowed:
        %! - will be replaced by the history event number
        %u - will be replaced by the NetScaler user name
        %h - will be replaced by the NetScaler hostname
        %t - will be replaced by the current time
        %T - will be replaced by the current time (24 hr format)
        %d - will be replaced by the current date
        %s - will be replaced by the node state



##Example

&gt; set cli prompt "%h %T" Donelb-ns1 15:16&gt;

##show cli prompt

Use this command to display the current CLI prompt, with special values like '%h' unexpanded.


##Synopsys

show cli prompt


##Outputs

<b>promptString</b>



##Example

10.101.4.22 15:20&gt; sh cli prompt        CLI prompt is set to "%h %T" Done

