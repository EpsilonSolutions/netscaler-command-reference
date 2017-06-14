#HA files

The following operations can be performed on "HA files":


##sync HA files

Synchronize various configuration files from the primary node to the secondary. You can run this command from either node. Files that are present on only the secondary and are specific to the secondary are not deleted. This command fails if the secondary node is disabled, the secondary node is not accessible from the primary, or you enter the command on a standalone appliance.


##Synopsys

sync HA files [&lt;Mode> ...]


##Arguments

<b>Mode</b>
Specify one of the following modes of synchronization.
* all - Synchronize files related to system configuration, Access Gateway bookmarks, SSL certificates, SSL CRL lists, HTML injection scripts, and Application Firewall XML objects. 
* bookmarks - Synchronize all Access Gateway bookmarks.
* ssl - Synchronize all certificates, keys, and CRLs for the SSL feature. 
* htmlinjection. Synchronize all scripts configured for the HTML injection feature. 
* imports. Synchronize all XML objects (for example, WSDLs, schemas, error pages) configured for the application firewall. 
* misc - Synchronize all license files and the rc.conf file. 
* all_plus_misc - Synchronize files related to system configuration, Access Gateway bookmarks, SSL certificates, SSL CRL lists, HTML injection scripts, application firewall XML objects, licenses, and the rc.conf file.



##Example

sync files all

