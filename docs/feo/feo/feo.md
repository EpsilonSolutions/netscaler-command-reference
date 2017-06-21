#feo

The following operations can be performed on "feo":


##stat feo

Shows front end optimization performance statistics.


##Synopsys

stat feo [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>detail</b>
Specifies detailed output (including more statistics). The output can be quite voluminous. Without this argument, the output will show only a summary.

<b>fullValues</b>
Specifies that numbers and strings should be displayed in their full form. Without this option, long strings are shortened and large numbers are abbreviated

<b>ntimes</b>
The number of times, in intervals of seven seconds, the statistics should be displayed.
Default value: 1
Minimum value: 0

<b>logFile</b>
The name of the log file to be used as input.

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>Optimized cache objects (VcDn)</b>
Total number of optimized cache objects ready to be served.

<b>Original cache objects (OcDn)</b>
Total number of original cache objects ready to be served.

<b>Domain Sharded (DmShd)</b>
Total no of images whose domain has been set from shards.

<b>Images lazy loaded (ImLzLd)</b>
Total number of images modified for lazy loading.

<b>URI Replaced (UrRep)</b>
Total number of URI replaced.

<b>Inlined Imgs in CSS (InCsIm)</b>
Total number of images inlined in CSS.

<b>Inlined JS (InJs)</b>
Total number of inlined JS files.

<b>Inlined CSS (InCs)</b>
Total number of inlined CSS files.

<b>Inlined images (InIm)</b>
Total number of inlined images in HTML.

<b>Data Savings in KB (DatSav)</b>
Total data savings in bytes.

<b>HTML comments removed (HtmCmtR)</b>
The total number of HTML comments removed.

<b>Cache extended (CacExt)</b>
The total number of objects cache extended.

<b>CSS combined (CssComb)</b>
The total number of CSS combined.

<b>Import to Links (ImpToLink)</b>
The total number of CSS imports converted to links

<b>JS moved to end (JsMoved)</b>
The total number of JS moved to end.

<b>CSS moved to head (CssMoved)</b>
The total number of CSS moved to head.

<b>JS Minifed (JsMin)</b>
The total number of JS files minified.

<b>CSS Minifed (CssMin)</b>
The total number of CSS files minified.

<b>Images to Jpegxr (ImgToJxr)</b>
The total number of images converted to JPEGXR format.

<b>Images to WebP (ImgToWebP)</b>
The total number of images converted to WEBP format.

<b>JPEGs Optimized (JpegsOpt)</b>
The total number of JPEG format images optimized.

<b>Gif to PNGs (GifToPng)</b>
The total number of images converted from GIF to PNG format.

<b>Images Resized (ImgResz)</b>
The total number of images resized to dimensions in the &lt;img> tag.



