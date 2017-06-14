#shell

The following operations can be performed on "shell":


##shell

Exits to the FreeBSD command prompt. Press Control + D or type exit to return to the NetScaler command prompt.Note: The shell can be accessed only by users who have write access to the NetScaler appliance.


##Synopsys

shell [(command)]


##Arguments

<b>command</b>
Shell command(s) to be invoked.



##Example

&gt; shell# ps | grep nscli485  p0  S      0:01.12 -nscli (nscli)590  p0  S+     0:00.00 grep nscli# ^D  Done&gt; shell ps -aux |grep nscli485  p0  S      0:01.12 -nscli (nscli)590  p0  S+     0:00.00 grep nscli

