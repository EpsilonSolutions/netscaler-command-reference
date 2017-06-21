#cli mode

The following operations can be performed on "cli mode":


[set](#set-cli-mode) | [unset](#unset-cli-mode) | [show](#show-cli-mode)

##set cli mode

Use this command to specify how the CLI should display command output.


##Synopsys

set cli mode [-page ( ON | OFF )] [-total ( ON | OFF )] [-color ( ON | OFF )] [-disabledFeatureAction &lt;disabledFeatureAction>] [-timeout &lt;secs>] [-regex ( ON | OFF )]


##Arguments

<b>page</b>
Determines whether output that spans more than one screen is "paged".  Specify ON to pause the display after each screen of ouput.
Possible values: ON, OFF
Default value: OFF

<b>total</b>
Determines whether CLI "show" commands display a total count of objects before displaying the objects themselves.
Possible values: ON, OFF
Default value: OFF

<b>color</b>
Specifies whether output can be shown in color, if the terminal supports it.
Possible values: ON, OFF
Default value: OFF

<b>disabledFeatureAction</b>
Specifies what will happen when a configuration command is issued for a disabled feature. The following values are allowed:
	NONE - The action is allowed, and no warning message is issued.;
	ALLOW - The action is allowed, but a warning message is issued.;
	DENY - The action is not allowed.
Possible values: NONE, ALLOW, DENY
Default value: NS_ALLOW

<b>timeout</b>
CLI session inactivity timeout, in seconds. If Restrictedtimeout argument of system parameter is enabled, Timeout can have values in the range [300-86400] seconds and also climode timeout cannot be configured beyond admin configured value. If Restrictedtimeout argument of system parameter is disabled, Timeout can have values in the range [0, 10-100000000] seconds. Default value is 900 seconds.
Default value: -1

<b>regex</b>
If ON, regular expressions can be used as argument values
Possible values: ON, OFF
Default value: ON



##unset cli mode

Use this command to remove cli mode settings.Refer to the set cli mode command for meanings of the arguments.


##Synopsys

unset cli mode [-page] [-total] [-color] [-disabledFeatureAction] [-timeout] [-regex]


##show cli mode

Use this command to display the current settings of parameters that can be set with the 'set cli mode' command.


##Synopsys

show cli mode


##Outputs

<b>page</b>
Determines whether output that spans more than one screen is "paged".  Specify ON to pause the display after each screen of ouput.

<b>total</b>
Determines whether CLI "show" commands display a total count of objects before displaying the objects themselves.

<b>color</b>
Specifies whether output can be shown in color, if the terminal supports it.

<b>disabledFeatureAction</b>
Specifies what will happen when a configuration command is issued for a disabled feature. The following values are allowed:
	NONE - The action is allowed, and no warning message is issued.;
	ALLOW - The action is allowed, but a warning message is issued.;
	DENY - The action is not allowed.

<b>argMark</b>
mark

<b>noLicenseAction</b>
no licence

<b>diagLevel</b>
diagnostic level

<b>timeout</b>
CLI session inactivity timeout, in seconds. If Restrictedtimeout argument of system parameter is enabled, Timeout can have values in the range [300-86400] seconds and also climode timeout cannot be configured beyond admin configured value. If Restrictedtimeout argument of system parameter is disabled, Timeout can have values in the range [0, 10-100000000] seconds. Default value is 900 seconds.

<b>timeoutKind</b>
From where the timeout has been inherited.

<b>regex</b>
If ON, regular expressions can be used as argument values

<b>r</b>
regular expression

<b>format</b>
format

<b>stats</b>

<b>serverPort</b>



