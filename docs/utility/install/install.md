#install

The following operations can be performed on "install":


##install

Installs a version of NetScaler software on the system.


##Synopsys

install &lt;url> [-y] [-L] [-enhancedUpgrade] [-resizeSwapVar]


##Arguments

<b>url</b>
Url for the build file. Must be in the following formats:
http://[user]:[password]@host/path/to/file
https://[user]:[password]@host/path/to/file
sftp://[user]:[password]@host/path/to/file
scp://[user]:[password]@host/path/to/file
ftp://[user]:[password]@host/path/to/file
file://path/to/file

<b>y</b>
Do not prompt for yes/no before rebooting.

<b>L</b>
Use this flag to enable callhome.

<b>enhancedUpgrade</b>
Use this flag for upgrading from/to enhancement mode.

<b>resizeSwapVar</b>
Use this flag to change swap size on ONLY 64bit nCore/MCNS/VMPE systems NON-VPX systems.



##Example

install http://host.netscaler.com/ns-6.0-41.2.tgz

