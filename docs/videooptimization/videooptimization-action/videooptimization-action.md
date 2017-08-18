#videooptimization action

The following operations can be performed on "videooptimization action":


[add](#add-videooptimization-action) | [rm](#rm-videooptimization-action) | [show](#show-videooptimization-action) | [set](#set-videooptimization-action) | [unset](#unset-videooptimization-action) | [rename](#rename-videooptimization-action)

##add videooptimization action

Creates a video optimization action, which specifies detected media type.Note: The following Detection actions are pre-configured by default:DETECT_CLEARTEXT_PD, DETECT_CLEARTEXT_ABR, DETECT_ENCRYPTED_ABR, TRIGGER_ENC_ABR_DETECTION


##Synopsys

add videooptimization action &lt;name> -type &lt;type> [-rate &lt;integer>] [-comment &lt;string>]


##Arguments

<b>name</b>
Name for the video optimization action. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters.

<b>type</b>
Type of video optimization action. Available settings function as follows:
* clear_text_pd - Cleartext PD type is detected.
* clear_text_abr - Cleartext ABR is detected.
* encrypted_abr - Encrypted ABR is detected.
* trigger_enc_abr - Possible encrypted ABR is detected.
* optimize_abr - Optimize detected ABR
Possible values: clear_text_pd, clear_text_abr, encrypted_abr, trigger_enc_abr, optimize_abr

<b>rate</b>
ABR Optimization Rate (in Kbps)
Default value: 1000
Minimum value: 1
Maximum value: 2147483647

<b>comment</b>
Comment. Any type of information about this video optimization action.



##rm videooptimization action

Removes the specified video optimization action.


##Synopsys

rm videooptimization action &lt;name>


##Arguments

<b>name</b>
Name of the video optimization action to remove.



##Example

rm videooptimization action act_before

##show videooptimization action

Name of the video optimization action for which to display the current settings. If you do not set this parameter current settings are shown for all video optimization actions.


##Synopsys

show videooptimization action [&lt;name>]


##Arguments

<b>name</b>
Name of the video optimization action.



##Outputs

<b>stateflag</b>

<b>type</b>
Type of video optimization action. It can be: (clear_text_pd).

<b>hits</b>
The number of times the action has been taken.

<b>referenceCount</b>
The number of references to the action.

<b>undefHits</b>
The number of times the action resulted in UNDEF.

<b>rate</b>
ABR Optimization Rate (in Kbps)

<b>comment</b>
Comment. Any type of information about this video optimization action.

<b>builtin</b>
Flag to determine whether video optimization action is built-in or not

<b>devno</b>

<b>count</b>



##Example

show videooptimization action DETECT_CLEARTEXT_PD

##set videooptimization action

Modifies the specified parameters of a video optimization action.


##Synopsys

set videooptimization action &lt;name> [-type &lt;type>  -rate &lt;integer>] [-comment &lt;string>]


##Arguments

<b>name</b>
Name of the video optimization action to be modified.

<b>type</b>
Type of video optimization action. It can be: (optimize_abr).
Possible values: clear_text_pd, clear_text_abr, encrypted_abr, trigger_enc_abr, optimize_abr

<b>rate</b>
ABR Optimization Rate (in Kbps)
Default value: 1000
Minimum value: 1
Maximum value: 2147483647

<b>comment</b>
Comment. Any type of information about this video optimization action.



##Example

set videooptimization  action act_vo -rate 2000

##unset videooptimization action

Use this command to remove videooptimization action settings.Refer to the set videooptimization action command for meanings of the arguments.


##Synopsys

unset videooptimization action &lt;name> [-rate] [-comment]


##rename videooptimization action

Renames a videooptimization action.


##Synopsys

rename videooptimization action &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the videooptimization action.

<b>newName</b>
New name for the videooptimization action.
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters.



##Example

rename videooptimization action oldname newname

