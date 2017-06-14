#cluster files

The following operations can be performed on "cluster files":


##sync cluster files

Synchronizes SSL Certificates, SSL CRL lists, SSL VPN bookmarks, and other files from the configuration coordinator (CCO) to the other cluster nodes. Execute this command from the cluster IP address only. This command is automatically triggered from the CCO when a new node is added to a cluster and periodically triggered to synchronize updated files between the cluster nodes.Note: Files on non-CCO nodes are not deleted if they do no not exist on the CCO.


##Synopsys

sync cluster files [&lt;Mode> ...]


##Arguments

<b>Mode</b>
The directories and files to be synchronized. The available settings function as follows:
 Mode    Paths
 all           /nsconfig/ssl/
                /var/netscaler/ssl/
                /var/vpn/bookmark/
                /nsconfig/dns/
                /nsconfig/htmlinjection/
                /netscaler/htmlinjection/ens/
                /nsconfig/monitors/
                /nsconfig/nstemplates/
                /nsconfig/ssh/
                /nsconfig/rc.netscaler
                /nsconfig/resolv.conf
                /nsconfig/inetd.conf
                /nsconfig/syslog.conf
                /nsconfig/snmpd.conf
                /nsconfig/ntp.conf
                /nsconfig/httpd.conf
                /nsconfig/sshd_config
                /nsconfig/hosts
                /nsconfig/enckey
                /var/nslw.bin/etc/krb5.conf
                /var/nslw.bin/etc/krb5.keytab
                /var/lib/likewise/db/
                /var/download/
                /var/wi/tomcat/webapps/
                /var/wi/tomcat/conf/Catalina/localhost/
                /var/wi/java_home/lib/security/cacerts
                /var/wi/java_home/jre/lib/security/cacerts
                /var/netscaler/locdb/
ssl            /nsconfig/ssl/
                 /var/netscaler/ssl/
bookmarks     /var/vpn/bookmark/
dns                  /nsconfig/dns/
htmlinjection    /nsconfig/htmlinjection/
imports          /var/download/
misc               /nsconfig/license/
                       /nsconfig/rc.conf
all_plus_misc    Includes *all* files and /nsconfig/license/ and /nsconfig/rc.conf.
Default value: all



##Example

sync cluster files ssl or sync cluster files all

