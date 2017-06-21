#ns extension

The following operations can be performed on "ns extension":


[import](#import-ns-extension) | [rm](#rm-ns-extension) | [add](#add-ns-extension) | [update](#update-ns-extension) | [set](#set-ns-extension) | [unset](#unset-ns-extension) | [show](#show-ns-extension)

##import ns extension

Imports the specified extension to the NetScaler appliance, assigns it the specified name, and stores it in the list of extension objects.


##Synopsys

import ns extension &lt;src> &lt;name> [-comment &lt;string>] [-overwrite]


##Arguments

<b>src</b>
Local path to and name of, or URL (protocol, host, path, and file name) for, the file in which to store the imported extension.
NOTE: The import fails if the object to be imported is on an HTTPS server that requires client certificate authentication for access.

<b>name</b>
Name to assign to the extension object on the NetScaler appliance.

<b>comment</b>
Any comments to preserve information about the extension object.

<b>overwrite</b>
Overwrites the existing file



##Example

import ns extension http://www.example.com/extension.lua my-extension 

##rm ns extension

Removes the specified extension object.


##Synopsys

rm ns extension &lt;name>


##Arguments

<b>name</b>
Name of the extension object to remove.



##Example

rm ns extension my-extension

##add ns extension

Add the specified extension object.


##Synopsys

add ns extension &lt;name> [-comment &lt;string>]


##Arguments

<b>name</b>
Name to assign to the extension object on the NetScaler appliance.

<b>comment</b>
Any comments to preserve information about the extension object.



##Example

add ns extension my-extension 

##update ns extension

Update the specified extension object.


##Synopsys

update ns extension &lt;name>


##Arguments

<b>name</b>
Name to assign to the extension object on the NetScaler appliance.



##Example

update ns extension my-extension 

##set ns extension

Modifies properties of the extension, including the comment and tracing. Note that tracing parameters are not preserved by a save config and so do not survive a reboot.


##Synopsys

set ns extension &lt;name> [-trace &lt;trace>] [-traceFunctions &lt;string>] [-traceVariables &lt;string>] [-comment &lt;string>]


##Arguments

<b>name</b>
Name to assign to the extension object on the NetScaler appliance.

<b>trace</b>
Enables tracing to the NS log file of extension execution:
   off   - turns off tracing (equivalent to unset ns extension &lt;extension-name&gt; -trace)
   calls - traces extension function calls with arguments and function returns with the first return value
   lines - traces the above plus line numbers for executed extension lines
   all   - traces the above plus local variables changed by executed extension lines
Note that the DEBUG log level must be enabled to see extension tracing.
This can be done by set audit syslogParams -loglevel ALL or -loglevel DEBUG.
Possible values: off, calls, lines, all
Default value: off

<b>traceFunctions</b>
Comma-separated list of extension functions to trace. By default, all extension functions are traced.

<b>traceVariables</b>
Comma-separated list of variables (in traced extension functions) to trace. By default, all variables are traced.

<b>comment</b>
Any comments to preserve information about the extension object.



##Example

set ns extension &lt;extension name&gt; -tracing all

##unset ns extension

Use this command to remove ns extension settings.Refer to the set ns extension command for meanings of the arguments.


##Synopsys

unset ns extension &lt;name> [-trace] [-traceFunctions] [-traceVariables] [-comment]


##show ns extension

Displays the specified extension object.


##Synopsys

show ns extension [&lt;name>] [-detail ( brief | all )]


##Arguments

<b>name</b>
Name of the extension object.

<b>detail</b>
Show detail for extension function.
Possible values: brief, all



##Outputs

<b>stateflag</b>

<b>src</b>
Local path to and name of, or URL (protocol, host, path, and file name) for, the file in which to store the imported extension.
NOTE: The import fails if the object to be imported is on an HTTPS server that requires client certificate authentication for access.

<b>type</b>

<b>extensionFunctionName</b>
Name of extension function given in the extension.

<b>extensionFunctionLineNumber</b>
Line number of the function in file.

<b>extensionFunctionClassType</b>
Extension function class type.

<b>extensionFunctionClasses</b>
List of classes (including inherited) that the function is present in.

<b>extensionFunctionClassesCount</b>
Number of classes the function is present in.

<b>extensionFunctionReturnType</b>
Extension function return type.

<b>activeExtensionFunction</b>
Extension function is in use or not.

<b>extensionFunctionArgType</b>
List of extension function's arguments types

<b>extensionFunctionAllParams</b>
List of parameters (including promotions) that the function can accept.

<b>extensionFunctionAllParamsCount</b>
Number of parameters (including promotions) that the function can accept.

<b>extensionFuncDescription</b>
Any description to preserve information about the extension function.

<b>extensionFunctionArgCount</b>
Number of parameters in the extension function

<b>comment</b>
Any comments to preserve information about the extension object.

<b>functionHits</b>
Number of time function evaluates successfully.

<b>functionUndefHits</b>
Number of times error occured in evaluating extension function.

<b>functionHaltCount</b>
Number of time function evaluation is halted.

<b>trace</b>
Enables tracing to the NS log file of extension execution:
   off   - turns off tracing (equivalent to unset ns extension &lt;extension-name> -trace)
   calls - traces extension function calls with arguments and function returns with the first return value
   lines - traces the above plus line numbers for executed extension lines
   all   - traces the above plus local variables changed by executed extension lines
Note that the DEBUG log level must be enabled to see extension tracing.
This can be done by set audit syslogParams -loglevel ALL or -loglevel DEBUG.

<b>traceFunctions</b>
Comma-separated list of extension functions to trace. By default, all extension functions are traced.

<b>traceVariables</b>
Comma-separated list of variables (in traced extension functions) to trace. By default, all variables are traced.

<b>devno</b>

<b>count</b>



##Example

show ns extension my-extension

