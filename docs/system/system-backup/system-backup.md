#system backup

The following operations can be performed on "system backup":


[create](#create-system-backup) | [restore](#restore-system-backup) | [rm](#rm-system-backup) | [show](#show-system-backup)

##create system backup

Creates a backup file (*.tgz) that is stored in the /var/ns_sys_backup/ directory. This file can be used to restore the appliance by using the "restore system backup" command.


##Synopsys

create system backup [&lt;fileName>] [-level ( basic | full )] [-comment &lt;string>]


##Arguments

<b>fileName</b>
Name of the backup file(*.tgz) to be restored.

<b>level</b>
Level of data to be backed up.
Possible values: basic, full
Default value: basic

<b>comment</b>
Comment specified at the time of creation of the backup file(*.tgz).



##restore system backup

Restores an appliance by using the backup file (*.tgz) that was created by using the "create system backup" command.


##Synopsys

restore system backup &lt;fileName>


##Arguments

<b>fileName</b>
Name of the backup file(*.tgz) to be restored.



##rm system backup

Removes a backup file (*.tgz) that was created by using the "create system backup" command.


##Synopsys

rm system backup &lt;fileName>


##Arguments

<b>fileName</b>
Name of the backup file(*.tgz) to be restored.



##show system backup

Retrieves the backed up files that were created in the appliance.


##Synopsys

show system backup [&lt;fileName>]


##Arguments

<b>fileName</b>
Name of the backup file(*.tgz) to be restored.



##Outputs

<b>level</b>
Level of data to be backed up.

<b>comment</b>
Comment specified at the time of creation of the backup file(*.tgz).

<b>size</b>
Size of the backup file(*.tgz) in KB.

<b>creationTime</b>
Creation time of the backup file(*.tgz).

<b>version</b>
Build version of the backup file(*.tgz).

<b>createdBy</b>
Name of user who created the backup file(*.tgz).

<b>IPAddress</b>
Ip of Netscaler box where the backup file(*.tgz) was created.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



