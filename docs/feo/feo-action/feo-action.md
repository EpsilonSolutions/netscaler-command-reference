#feo action

The following operations can be performed on "feo action":


[add](#add-feo-action) | [set](#set-feo-action) | [unset](#unset-feo-action) | [rm](#rm-feo-action) | [show](#show-feo-action)

##add feo action

Create a front end optimization action.


##Synopsys

add feo action &lt;name> [-pageExtendCache] [&lt;cacheMaxage>] [-imgShrinkToAttrib] [-imgGifToPng] [-imgToWebp] [-imgToJpegXR] [-imgInline] [-cssImgInline] [-jpgOptimize] [-imgLazyLoad] [-cssMinify] [-cssInline] [-cssCombine] [-convertImportToLink] [-jsMinify] [-jsInline] [-htmlMinify] [-cssMoveToHead] [-jsMoveToEND] [-domainSharding &lt;string>  &lt;dnsShards> ...] [-clientSideMeasurements]


##Arguments

<b>name</b>
The name of the front end optimization action.

<b>pageExtendCache</b>
Extend the time period during which the browser can use the cached resource.

<b>cacheMaxage</b>
Maxage for cache extension.
Default value: 30
Minimum value: 0
Maximum value: 360

<b>imgShrinkToAttrib</b>
Shrink image dimensions as per the height and width attributes specified in the &lt;img&gt; tag.

<b>imgGifToPng</b>
Convert GIF image formats to PNG formats.

<b>imgToWebp</b>
Convert JPEG, GIF, PNG image formats to WEBP format.

<b>imgToJpegXR</b>
Convert JPEG, GIF, PNG image formats to JXR format.

<b>imgInline</b>
Inline images whose size is less than 2KB.

<b>cssImgInline</b>
Inline small images (less than 2KB) referred within CSS files as background-URLs

<b>jpgOptimize</b>
Remove non-image data such as comments from JPEG images.

<b>imgLazyLoad</b>
Download images, only when the user scrolls the page to view them.

<b>cssMinify</b>
Remove comments and whitespaces from CSSs.

<b>cssInline</b>
Inline CSS files, whose size is less than 2KB, within the main page.

<b>cssCombine</b>
Combine one or more CSS files into one file.

<b>convertImportToLink</b>
Convert CSS import statements to HTML link tags.

<b>jsMinify</b>
Remove comments and whitespaces from JavaScript.

<b>jsInline</b>
Convert linked JavaScript files (less than 2KB) to inline JavaScript files.

<b>htmlMinify</b>
Remove comments and whitespaces from an HTML page.

<b>cssMoveToHead</b>
Move any CSS file present within the body tag of an HTML page to the head tag.

<b>jsMoveToEND</b>
Move any JavaScript present in the body tag to the end of the body tag.

<b>domainSharding</b>
Domain name of the server

<b>dnsShards</b>
Set of domain names that replaces the parent domain.

<b>clientSideMeasurements</b>
Send AppFlow records about the web pages optimized by this action. The records provide FEO statistics, such as the number of HTTP requests that have been reduced for this page. You must enable the Appflow feature before enabling this parameter.



##set feo action

Modify a front end optimization action.


##Synopsys

set feo action &lt;name> [-pageExtendCache] [&lt;cacheMaxage>] [-imgShrinkToAttrib] [-imgGifToPng] [-imgToWebp] [-imgToJpegXR] [-imgInline] [-cssImgInline] [-jpgOptimize] [-imgLazyLoad] [-cssMinify] [-cssInline] [-cssCombine] [-convertImportToLink] [-jsMinify] [-jsInline] [-htmlMinify] [-cssMoveToHead] [-jsMoveToEND] [-domainSharding &lt;string>  &lt;dnsShards> ...] [-clientSideMeasurements]


##Arguments

<b>name</b>
The name of the front end optimization action.

<b>pageExtendCache</b>
Extend the time period during which the browser can use the cached resource.

<b>cacheMaxage</b>
Maxage for cache extension.
Default value: 30
Minimum value: 0
Maximum value: 360

<b>imgShrinkToAttrib</b>
Shrink image dimensions as per the height and width attributes specified in the &lt;img&gt; tag.

<b>imgGifToPng</b>
Convert GIF image formats to PNG formats.

<b>imgToWebp</b>
Convert JPEG, GIF, PNG image formats to WEBP format.

<b>imgToJpegXR</b>
Convert JPEG, GIF, PNG image formats to JXR format.

<b>imgInline</b>
Inline images whose size is less than 2KB.

<b>cssImgInline</b>
Inline small images (less than 2KB) referred within CSS files as background-URLs

<b>jpgOptimize</b>
Remove non-image data such as comments from JPEG images.

<b>imgLazyLoad</b>
Download images, only when the user scrolls the page to view them.

<b>cssMinify</b>
Remove comments and whitespaces from CSSs.

<b>cssInline</b>
Inline CSS files, whose size is less than 2KB, within the main page.

<b>cssCombine</b>
Combine one or more CSS files into one file.

<b>convertImportToLink</b>
Convert CSS import statements to HTML link tags.

<b>jsMinify</b>
Remove comments and whitespaces from JavaScript.

<b>jsInline</b>
Convert linked JavaScript files (less than 2KB) to inline JavaScript files.

<b>htmlMinify</b>
Remove comments and whitespaces from an HTML page.

<b>cssMoveToHead</b>
Move any CSS file present within the body tag of an HTML page to the head tag.

<b>jsMoveToEND</b>
Move any JavaScript present in the body tag to the end of the body tag.

<b>domainSharding</b>
Domain name of the server

<b>dnsShards</b>
Set of domain names that replaces the parent domain.

<b>clientSideMeasurements</b>
Send AppFlow records about the web pages optimized by this action. The records provide FEO statistics, such as the number of HTTP requests that have been reduced for this page. You must enable the Appflow feature before enabling this parameter.



##unset feo action

Modify a front end optimization action..Refer to the set feo action command for meanings of the arguments.


##Synopsys

unset feo action &lt;name> [-pageExtendCache] [-imgShrinkToAttrib] [-imgGifToPng] [-imgToWebp] [-imgToJpegXR] [-imgInline] [-cssImgInline] [-jpgOptimize] [-imgLazyLoad] [-cssMinify] [-cssInline] [-cssCombine] [-convertImportToLink] [-jsMinify] [-jsInline] [-htmlMinify] [-cssMoveToHead] [-jsMoveToEND] [-clientSideMeasurements] [-domainSharding]


##rm feo action

Remove the specified front end optimization action.


##Synopsys

rm feo action &lt;name>


##Arguments

<b>name</b>
The name of the front end optimization action.



##show feo action

Display the front end optimization actions defined, including the built-in actions.


##Synopsys

show feo action [&lt;name>]


##Arguments

<b>name</b>
The name of the front end optimization action.



##Outputs

<b>stateflag</b>

<b>pageExtendCache</b>
Extend the time period during which the browser can use the cached resource.

<b>cacheMaxage</b>
Maxage for cache extension.

<b>imgShrinkToAttrib</b>
Shrink image dimensions as per the height and width attributes specified in the &lt;img> tag.

<b>imgGifToPng</b>
Convert GIF image formats to PNG formats.

<b>imgToWebp</b>
Convert JPEG, GIF, PNG image formats to WEBP format.

<b>imgToJpegXR</b>
Convert JPEG, GIF, PNG image formats to JXR format.

<b>imgAddDimensions</b>
Add dimension attributes to images, if not specified within the &lt;img> tag.

<b>imgShrinkForMobile</b>
Serve smaller images for mobile users.

<b>imgWeaken</b>
Reduce the image quality.

<b>imgInline</b>
Inline images whose size is less than 2KB.

<b>cssImgInline</b>
Inline small images (less than 2KB) referred within CSS files as background-URLs

<b>jpgOptimize</b>
Remove non-image data such as comments from JPEG images.

<b>jpgProgressive</b>
Convert JPEG image formats to progressive formats.

<b>imgLazyLoad</b>
Download images, only when the user scrolls the page to view them.

<b>cssMinify</b>
Remove comments and whitespaces from CSSs.

<b>cssInline</b>
Inline CSS files, whose size is less than 2KB, within the main page.

<b>cssCombine</b>
Combine one or more CSS files into one file.

<b>cssFlattenImports</b>
Replace CSS import statements with the file content.

<b>convertImportToLink</b>
Convert CSS import statements to HTML link tags.

<b>jsMinify</b>
Remove comments and whitespaces from JavaScript.

<b>jsInline</b>
Convert linked JavaScript files (less than 2KB) to inline JavaScript files.

<b>jsCombine</b>
Combine one or more JavaScript files into one file.

<b>htmlMinify</b>
Remove comments and whitespaces from an HTML page.

<b>htmlRmDefaultAttribs</b>
Remove default redundant attributes from an HTML file.

<b>htmlRmAttribQuotes</b>
Remove unnecessary quotes present within the HTML attributes.

<b>htmlTrimUrls</b>
Trim URLs.

<b>cssMoveToHead</b>
Move any CSS file present within the body tag of an HTML page to the head tag.

<b>jsMoveToEND</b>
Move any JavaScript present in the body tag to the end of the body tag.

<b>domainSharding</b>
Domain name of the server

<b>dnsShards</b>
Set of domain names that replaces the parent domain.

<b>clientSideMeasurements</b>
Send AppFlow records about the web pages optimized by this action. The records provide FEO statistics, such as the number of HTTP requests that have been reduced for this page. You must enable the Appflow feature before enabling this parameter.

<b>hits</b>
The number of times the action has been taken.

<b>undefHits</b>
Total number of undefined policy hits.

<b>builtin</b>
Flag to determine if front end optimization action is built-in or not.

<b>devno</b>

<b>count</b>



