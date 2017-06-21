#techsupport

The following operations can be performed on "techsupport":


##show techsupport

Generates a gzipped tar archive of system configuration data and statistics. To minimize archive file size newnslog collection is restricted to 500mb, 6 files, or 7 days, whichever occurs first. If older data is needed, it may require manual collection. The archive should be submitted to Citrix Technical Support for further analysis and is available at the following path:/var/tmp/support/support.tgz.The above path is a symlink to the most recent collector for easy access. The full filename varies based on deployment topology but generally follows a format similar to:collector_&lt;NS IP>_&lt;P/S>_&lt;DateTime>.tgz.The output path and filename are displayed to the user when the command is executed.


##Synopsys

show techsupport [-scope &lt;scope>  &lt;partitionName>] [-upload  [-proxy &lt;string>]  [-casenumber &lt;string>]  [-file &lt;string>]  [-description &lt;string>]]


##Arguments

<b>scope</b>
Use this option to gather data on the present node, all cluster nodes, or for the specified partitions. The CLUSTER scope generates smaller abbreviated archives for all nodes. The PARTITION scope collects the admin partition in addition to those specified. The partitionName option is only required for the PARTITION scope.
Possible values: NODE, CLUSTER, PARTITION
Default value: NODE

<b>partitionName</b>
Name of the partition

<b>upload</b>
Securely upload the collector archive to Citrix Technical Support using SSL. MyCitrix credentials will be required. If used with the -file option, no new collector archive is generated. Instead, the specified archive is uploaded. Note that the upload operation time depends on the size of the archive file, and the connection bandwidth.

<b>proxy</b>
Specifies the proxy server to be used when uploading a collector archive. Use this parameter if the NetScaler appliance does not have direct internet connectivity. The basic format of the proxy string is: "proxy_IP:&lt;proxy_port&gt;" (without quotes). If the proxy requires authentication the format is: "username:password@proxy_IP:&lt;proxy_port&gt;"

<b>casenumber</b>
Specifies the associated case or service request number if it has already been opened with Citrix Technical Support.

<b>file</b>
Specifies the name (with full path) of the collector archive file to be uploaded. If this is specified, no new collector archive is generated.

<b>description</b>
Provides a text description for the the upload, and can be used for logging purposes.



##Outputs

<b>response</b>
Output as text printed to console and syslog at NOTICE level.

<b>serverName</b>



##Example

show techsupportshow techsupport -upload -case 71234567show techsupport -scope CLUSTER

