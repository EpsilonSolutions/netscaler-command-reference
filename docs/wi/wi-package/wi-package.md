#wi package

The following operations can be performed on "wi package":


[install](#install-wi-package) | [uninstall](#uninstall-wi-package) | [show](#show-wi-package)

##install wi package

Installs Web Interface and JRE tar files on the NetScaler appliance.


##Synopsys

install wi package [-jre &lt;URL>] [-wi &lt;URL>] [-maxSites &lt;maxSites>]


##Arguments

<b>jre</b>
Complete path to the JRE tar file.
You can use OpenJDK7 package for FreeBSD 8.x/amd64.The Java package can be downloaded from http://ftp-archive.freebsd.org/pub/FreeBSD-Archive/old-releases/amd64/amd64/8.4-RELEASE/packages/java/openjdk-7.17.02_2.tbz
Default value: "file://tmp/diablo-jdk-freebsd6.amd64.1.6.0.07.02.tbz"

<b>wi</b>
Complete path to the Web Interface tar file for installing the Web Interface on the NetScaler appliance. This file includes Apache Tomcat Web server. The file name has the following format: nswi-&lt;version number&gt;.tgz (for example, nswi-1.5.tgz).
Default value: "http://citrix.com/downloads/nswi-1.7.tgz"

<b>maxSites</b>
Maximum number of Web Interface sites that can be created on the NetScaler appliance; changes the amount of RAM reserved for Web Interface usage; changing its value results in restart of Tomcat server and invalidates any existing Web Interface sessions.
Possible values: 3, 25, 50, 100, 200, 500



##Example

install wi package -jre http://10.102.1.10/diablo-latte-freebsd6-amd64-1.6.0_07-b02.tar.bz2 -wi http://citrix.com/downloads/nswi-1.6.tgz -maxSites 25

##uninstall wi package

Removes the Web Interface and JRE tar files, and the entire Web Interface related configuration, from the NetScaler appliance.


##Synopsys

uninstall wi package


##Example

uninstall wi package

##show wi package

Show the installed wi package


##Synopsys

show wi package


##Outputs

<b>jre</b>
Complete path to the JRE tar file.
You can use OpenJDK7 package for FreeBSD 8.x/amd64.The Java package can be downloaded from http://ftp-archive.freebsd.org/pub/FreeBSD-Archive/old-releases/amd64/amd64/8.4-RELEASE/packages/java/openjdk-7.17.02_2.tbz

<b>wi</b>
Complete path to the Web Interface tar file for installing the Web Interface on the NetScaler appliance. This file includes Apache Tomcat Web server. The file name has the following format: nswi-&lt;version number>.tgz (for example, nswi-1.5.tgz).

<b>maxSites</b>
Maximum number of Web Interface sites that can be created on the NetScaler appliance; changes the amount of RAM reserved for Web Interface usage; changing its value results in restart of Tomcat server and invalidates any existing Web Interface sessions.



##Example

show wi package

