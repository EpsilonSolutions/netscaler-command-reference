#install

The following operations can be performed on "install":


##install

Installs a version of NetScaler software on the system.


##Synopsys

install &lt;url> [-c] [-y]


##Arguments

<b>url</b>
http://[user]:[password]@host/path/to/file
https://[user]:[password]@host/path/to/file
sftp://[user]:[password]@host/path/to/file
scp://[user]:[password]@host/path/to/file
ftp://[user]:[password]@host/path/to/file
file://path/to/file

<b>c</b>
Back up existing kernel.

<b>y</b>
Do not prompt for yes/no before rebooting.



##Example

install http://host.netscaler.com/ns-6.0-41.2.tgz

