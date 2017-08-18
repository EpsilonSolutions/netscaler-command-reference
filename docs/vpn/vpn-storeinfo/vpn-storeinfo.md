#vpn storeinfo

The following operations can be performed on "vpn storeinfo":


##show vpn storeinfo

Show the Store Front information summary


##Synopsys

show vpn storeinfo -url &lt;URL>


##Arguments

<b>url</b>
StoreFront URL to be scanned



##Outputs

<b>storeServerStatus</b>
Availability of the server for TCP connections

<b>storeServerIsSf</b>
Indicates if the server being scanned is running StoreFront.

<b>storeApiSupport</b>
Indicates StoreFront API support status

<b>storeList</b>
List of available stores return by StoreFront API

<b>storeStatus</b>
Availability of the specified StoreFront store

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show vpn storeinfo -url &lt;url&gt;

