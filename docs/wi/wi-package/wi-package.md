#wi package

The following operations can be performed on "wi package":


[install](#install-wi-package) | [uninstall](#uninstall-wi-package)

##install wi package

Installs Web Interface and JRE tar files on the NetScaler appliance.


##Synopsys

install wi package [-jre &lt;URL>] [-wi &lt;URL>] [-maxSites &lt;maxSites>]


##Arguments

<b>jre</b>
Complete path to the JRE tar file. 
You can use the Diablo Latte JRE version 1.6.0-7 for 64-bit FreeBSD 6.x/amd64 platform available on the FreeBSD Foundation web site.
Alternatively, you can use OpenJDK6 package for FreeBSD 6.x/amd63.The Java package can be downloaded from http://ftp.riken.jp/pub/FreeBSD/ports/amd64/packages-6-stable/java/openjdk6-b17_2.tbz or http://www.freebsdfoundation.org/cgi-bin/download?download=diablo-jdk-freebsd6.amd64.1.6.0.07.02.tbz
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

