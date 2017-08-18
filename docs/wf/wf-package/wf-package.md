#wf package

The following operations can be performed on "wf package":


[install](#install-wf-package) | [uninstall](#uninstall-wf-package) | [show](#show-wf-package)

##install wf package

Installs WebFront and JRE tar files on the NetScaler appliance.


##Synopsys

install wf package [-jre &lt;URL>] [-wf &lt;URL>]


##Arguments

<b>jre</b>
Complete path to the JRE tar file. 
You can use OpenJDK7 package for FreeBSD 8.x/amd64.The Java package can be downloaded from http://ftp-archive.freebsd.org/pub/FreeBSD-Archive/old-releases/amd64/amd64/8.4-RELEASE/packages/java/openjdk-7.17.02_2.tbz or http://www.freebsdfoundation.org/cgi-bin/download?download=diablo-jdk-freebsd6.amd64.1.7.17.07.02.tbz

<b>wf</b>
Complete path to the WebFront tar file for installing the WebFront on the NetScaler appliance. This file includes Apache Tomcat Web server. The file name has the following format: nswf-&lt;version number&gt;.tar (for example, nswf-1.5.tar).



##Example

install wf package -jre file:///var/openjdk-7.17.02_2.tbz -wf file:///var/nswf-1.0.tar 

##uninstall wf package

Removes the WebFront and JRE tar files, and the entire WebFront related configuration, from the NetScaler appliance.


##Synopsys

uninstall wf package


##Example

uninstall wf package

##show wf package

Show the installed WebFront package


##Synopsys

show wf package


##Outputs

<b>jre</b>
Complete path to the JRE tar file. 
You can use OpenJDK7 package for FreeBSD 8.x/amd64.The Java package can be downloaded from http://ftp-archive.freebsd.org/pub/FreeBSD-Archive/old-releases/amd64/amd64/8.4-RELEASE/packages/java/openjdk-7.17.02_2.tbz or http://www.freebsdfoundation.org/cgi-bin/download?download=diablo-jdk-freebsd6.amd64.1.7.17.07.02.tbz

<b>wf</b>
Complete path to the WebFront tar file for installing the WebFront on the NetScaler appliance. This file includes Apache Tomcat Web server. The file name has the following format: nswf-&lt;version number>.tar (for example, nswf-1.5.tar).



##Example

show wf package

