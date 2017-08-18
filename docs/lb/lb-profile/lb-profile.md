#lb profile

The following operations can be performed on "lb profile":


[add](#add-lb-profile) | [rm](#rm-lb-profile) | [set](#set-lb-profile) | [unset](#unset-lb-profile) | [show](#show-lb-profile)

##add lb profile

Creates a LB profile.


##Synopsys

add lb profile &lt;lbprofilename> [-dbsLb ( ENABLED | DISABLED )] [-processLocal ( ENABLED | DISABLED )] [-httpOnlyCookieFlag ( ENABLED | DISABLED )] [-cookiePassphrase ] [-useEncryptedPersistenceCookie ( ENABLED | DISABLED )]


##Arguments

<b>lbprofilename</b>
Name of the LB profile.

<b>dbsLb</b>
Enable database specific load balancing for MySQL and MSSQL service types.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>processLocal</b>
By turning on this option packets destined to a vserver in a cluster will not under go any steering. Turn this option for single pa
cket request response mode or when the upstream device is performing a proper RSS for connection based distribution.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>httpOnlyCookieFlag</b>
Include the HttpOnly attribute in persistence cookies. The HttpOnly attribute limits the scope of a cookie to HTTP requests and helps mitigate the risk of cross-site scripting attacks.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>cookiePassphrase</b>
Use this parameter to specify the passphrase used to generate secured persistence cookie value. It specifies the passphrase with a maximum of 31 characters.

<b>useEncryptedPersistenceCookie</b>
Encode persistence cookie values using SHA2 hash.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##rm lb profile

Removes a LB profile from the device.


##Synopsys

rm lb profile &lt;lbprofilename>


##Arguments

<b>lbprofilename</b>
Name of the LB profile.



##set lb profile

Modify the specific parameters of LB profile.


##Synopsys

set lb profile &lt;lbprofilename> [-dbsLb ( ENABLED | DISABLED )] [-processLocal ( ENABLED | DISABLED )] [-httpOnlyCookieFlag ( ENABLED | DISABLED )] [-cookiePassphrase ] [-useEncryptedPersistenceCookie ( ENABLED | DISABLED )]


##Arguments

<b>lbprofilename</b>
Name of the LB profile.

<b>dbsLb</b>
Enable database specific load balancing for MySQL and MSSQL service types.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>processLocal</b>
By turning on this option packets destined to a vserver in a cluster will not under go any steering. Turn this option for single pa
cket request response mode or when the upstream device is performing a proper RSS for connection based distribution.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>httpOnlyCookieFlag</b>
Include the HttpOnly attribute in persistence cookies. The HttpOnly attribute limits the scope of a cookie to HTTP requests and helps mitigate the risk of cross-site scripting attacks.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>cookiePassphrase</b>
Use this parameter to specify the passphrase used to generate secured persistence cookie value. It specifies the passphrase with a maximum of 31 characters.

<b>useEncryptedPersistenceCookie</b>
Encode persistence cookie values using SHA2 hash.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##unset lb profile

Use this command to remove lb profile settings.Refer to the set lb profile command for meanings of the arguments.


##Synopsys

unset lb profile &lt;lbprofilename> [-dbsLb] [-processLocal] [-httpOnlyCookieFlag] [-cookiePassphrase] [-useEncryptedPersistenceCookie]


##show lb profile

Displays the list of lb profile/s in the device


##Synopsys

show lb profile [&lt;lbprofilename>]


##Arguments

<b>lbprofilename</b>
Name of the LB profile.



##Outputs

<b>dbsLb</b>
Enable database specific load balancing for MySQL and MSSQL service types.

<b>processLocal</b>
By turning on this option packets destined to a vserver in a cluster will not under go any steering. Turn this option for single pa
cket request response mode or when the upstream device is performing a proper RSS for connection based distribution.

<b>httpOnlyCookieFlag</b>
Include the HttpOnly attribute in persistence cookies. The HttpOnly attribute limits the scope of a cookie to HTTP requests and helps mitigate the risk of cross-site scripting attacks.

<b>cookiePassphrase</b>
Use this parameter to specify the passphrase used to generate secured persistence cookie value. It specifies the passphrase with a maximum of 31 characters.

<b>useSecuredPersistenceCookie</b>
Encode persistence cookie values using SHA2 hash.

<b>useEncryptedPersistenceCookie</b>
Encode persistence cookie values using SHA2 hash.

<b>vsvrcount</b>
Total number of vservers , the profile is bound to

<b>stateflag</b>
Flags controlling the display.

<b>devno</b>

<b>count</b>



