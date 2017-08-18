#videooptimization parameter

The following operations can be performed on "videooptimization parameter":


[set](#set-videooptimization-parameter) | [unset](#unset-videooptimization-parameter) | [show](#show-videooptimization-parameter)

##set videooptimization parameter

Modifies the specified Video Optimization parameters.


##Synopsys

set videooptimization parameter [-RandomSamplingPercentage &lt;number>]


##Arguments

<b>RandomSamplingPercentage</b>
Random Sampling Percentage.
Default value: 0
Minimum value: 0
Maximum value: 100



##Example

set videooptimization parameter -randomSamplingPercentage (20.00)

##unset videooptimization parameter

Use this command to remove videooptimization parameter settings.Refer to the set videooptimization parameter command for meanings of the arguments.


##Synopsys

unset videooptimization parameter -RandomSamplingPercentage


##show videooptimization parameter

Displays the Video Optimization parameters.


##Synopsys

show videooptimization parameter


##Outputs

<b>RandomSamplingPercentage</b>
Used to configure a percentage of user sessions that will be randomly selected for not being optimized.



##Example

show videooptimization parameter

