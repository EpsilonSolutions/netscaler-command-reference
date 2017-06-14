#feo parameter

The following operations can be performed on "feo parameter":


[set](#set-feo-parameter) | [unset](#unset-feo-parameter) | [show](#show-feo-parameter)

##set feo parameter

Configure front end optimization parameters.


##Synopsys

set feo parameter [-cacheMaxage &lt;positive_integer>] [-JpegQualityPercent &lt;positive_integer>] [-cssInlineThresSize &lt;positive_integer>] [-jsInlineThresSize &lt;positive_integer>] [-imgInlineThresSize &lt;positive_integer>]


##Arguments

<b>cacheMaxage</b>
Maximum period (in days), for cache extension.
Default value: 30
Minimum value: 0
Maximum value: 360

<b>JpegQualityPercent</b>
The percentage value of a JPEG image quality to be reduced. Range: 0 - 100
Default value: 75
Maximum value: 100

<b>cssInlineThresSize</b>
Threshold value of the file size (in bytes) for converting external CSS files to inline CSS files.
Default value: 1024
Minimum value: 1
Maximum value: 2048

<b>jsInlineThresSize</b>
Threshold value of the file size (in bytes), for converting external JavaScript files to inline JavaScript files.
Default value: 1024
Minimum value: 1
Maximum value: 2048

<b>imgInlineThresSize</b>
Maximum file size of an image (in bytes), for coverting linked images to inline images.
Default value: 1024
Minimum value: 1
Maximum value: 2048



##Example

set feo param -CacheMaxAge 8 -JpegQualityPercent 80 -cssInlineThresSize 1024 -jsInlineThresSize 1024 -imgInlineThresSize 1024

##unset feo parameter

Use this command to remove feo parameter settings.Refer to the set feo parameter command for meanings of the arguments.


##Synopsys

unset feo parameter [-cacheMaxage] [-JpegQualityPercent] [-cssInlineThresSize] [-jsInlineThresSize] [-imgInlineThresSize]


##show feo parameter

Display front end optimization parameters


##Synopsys

show feo parameter


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>cacheMaxage</b>
Maximum period (in days), for cache extension.

<b>JpegQualityPercent</b>
The percentage value of a JPEG image quality to be reduced. Range: 0 - 100

<b>cssInlineThresSize</b>
Threshold value of the file size (in bytes) for converting external CSS files to inline CSS files.

<b>jsInlineThresSize</b>
Threshold value of the file size (in bytes), for converting external JavaScript files to inline JavaScript files.

<b>imgInlineThresSize</b>
Maximum file size of an image (in bytes), for coverting linked images to inline images.



##Example

show feo param

