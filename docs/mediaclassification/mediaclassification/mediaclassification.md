#mediaclassification

The following operations can be performed on "mediaclassification":


##stat mediaclassification

Shows media classification statistics


##Synopsys

stat mediaclassification [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


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

<b>Total others served (MCOther)</b>

<b>Total videos served (McVideo)</b>

<b>Total audios served (McAudio)</b>

<b>MSsmoothStream videos (McMsSmthStrm)</b>
This tells the total number of Microsoft SmoothStreaming videos served by NS

<b>MSsmoothStream playlist (McMsSmthStreamingPl)</b>
This tells the total number of Microsoft SmoothStreaming playlist served by NS

<b>AppleLive videos (MCAppleLiveStrm)</b>
This tells the total number of AppleLive videos served by NS

<b>AppleLive playlist (McAppleLiveStrmPl)</b>
This tells the total number of AppleLive Playlist served by NS

<b>ADTS audios (McADTS)</b>
This tells the total number of ADTS audios served by NS

<b>AAC audios (McAAC)</b>
This tells the total number of AAC audios served by NS

<b>FLV videos (McFLV)</b>
This tells the total number of FLV videos served by NS

<b>MP4 videos (McMP4)</b>
This tells the total number of MP4 videos served by NS

<b>3GP videos (Mc3GP)</b>
This tells the total number of 3GP videos served by NS

<b>Total MSsmoothstream video bytes (McMsSthStrmBytes)</b>
This tells the total number of Microsoft SmoothStreaming video bytes served by NS

<b>Total MSsmoothStreamPL bytes (McMisftSmthStrmPlBytes)</b>
This tells the total number of Microsoft SmoothStreaming playlist bytes served by NS

<b>Total AppleLive video bytes (McAppleLiveStreamingBytes)</b>
This tells the total number of AppleLive video bytes served by NS

<b>Total AppleLive PL bytes (McAppleLiveStreamingPlaylistBytes)</b>
This tells the total number of AppleLive Playlist bytes served by NS

<b>Total ADTS audio bytes (McADTSbytes)</b>
This tells the total number of ADTS audio bytes served by NS

<b>Total AAC audio bytes (McAACbytes)</b>
This tells the total number of AAC bytes served by NS

<b>Total FLV video bytes (McFLVBytes)</b>
This tells the total number of FLV bytes served by NS

<b>Total MP4 video bytes (McMP4Bytes)</b>
This tells the total number of MP4 video bytes served by NS

<b>Total 3GP video bytes (Mc3GPBytes)</b>
This tells the total number of 3GP bytes served by NS

<b>Android requests (mcandroid)</b>
Total number of android requests to netscaler

<b>Laptop/Desktop requests (mclaptopDesktp)</b>
Total number of laptop/desktop requests to netscaler

<b>IOS requests (mcios)</b>
Total number of IOS requests to netscaler

<b>Other requests (mcother)</b>
Total number of other mobile device requests to netscaler

<b>Unidentified requests (mcunidentified)</b>
Total number of unidentified requests to netscaler

<b>Total responses served (McRes)</b>



