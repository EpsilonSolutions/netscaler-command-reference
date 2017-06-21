#ssl fips

The following operations can be performed on "ssl fips":


[set](#set-ssl-fips) | [unset](#unset-ssl-fips) | [reset](#reset-ssl-fips) | [show](#show-ssl-fips) | [update](#update-ssl-fips)

##set ssl fips

Initializes the Hardware Security Module (HSM) on the FIPS card and sets a new security officer password and user password.CAUTION: This command erases all data on the FIPS card. You are prompted before proceeding with the command execution. A restart is required before and after executing this command for the changes to apply. Save the configuration after executing this command and before restarting the appliance.


##Synopsys

set ssl fips -initHSM Level-2 [-hsmLabel &lt;string>]


##Arguments

<b>initHSM</b>
FIPS initialization level. The appliance currently supports Level-2 (FIPS 140-2).
Possible values: Level-2

<b>soPassword</b>
Security officer password that will be in effect after you have configured the HSM.

<b>oldSoPassword</b>
Old password for the security officer.

<b>userPassword</b>
The Hardware Security Module's (HSM) User password.

<b>hsmLabel</b>
Label to identify the Hardware Security Module (HSM).



##Example

1) set fips -initHSM Level-2 fipsso123 oldfipsso123 fipuser123 -hsmLabel FIPS-140-2&gt;This command will erase all data on the FIPS card. You must save the configuration (saveconfig) after executing this command.Do you want to continue?(Y/N)yThe above command initializes the FIPS card to FIPS-140-2 Level-2 and sets the HSM's Security Officer and User passwords.

##unset ssl fips

Use this command to remove ssl fips settings.Refer to the set ssl fips command for meanings of the arguments.


##Synopsys

unset ssl fips -hsmLabel


##reset ssl fips

Resets the FIPS card to the default password for Security Officer and User accounts. This command can be used only if the FIPS card has been locked because of three or more unsuccessful login attempts.


##Synopsys

reset ssl fips


##Example

reset fips

##show ssl fips

Displays the information on the FIPS card.


##Synopsys

show ssl fips


##Outputs

<b>initHSM</b>
The level of the FIPS initialization.

<b>soPassword</b>
Security officer password that will be in effect after you have configured the HSM.

<b>userPassword</b>
The Hardware Security Module's (HSM) User password.

<b>oldSoPassword</b>
Old password for the security officer.

<b>eraseData</b>
Erase data.

<b>hsmLabel</b>
FIPS card (HSM) label

<b>serial</b>
FIPS card serial number.

<b>majorVersion</b>
Firmware major version.

<b>minorVersion</b>
Firmware minor version.

<b>FipsHwMajorVersion</b>
FIPS card hardware major version.

<b>FipsHwMinorVersion</b>
FIPS card hardware minor version.

<b>FipsHwVersionString</b>
FIPS card hardware extended version string.

<b>flashMemoryTotal</b>
Total size of the flash memory on card.

<b>flashMemoryFree</b>
Total size of free flash memory.

<b>sramTotal</b>
Total size of the SRAM memory on card.

<b>sramFree</b>
Total size of free SRAM memory.

<b>status</b>
Status.

<b>flag</b>
Internal Flags.

<b>serialNo</b>
FIPS card serial number.

<b>model</b>
FIPS card model info.

<b>state</b>
FIPS card state.

<b>firmwareReleaseDate</b>
FIPS card firmware revision date.

<b>coresMax</b>
Maximum number of crypto cores present in the FIPS card.

<b>coresEnabled</b>
Number of crypto cores enabled in the FIPS card.



##Example

An example of the output for show ssl fips command is as follows:	FIPS HSM Info:		HSM Label              : FIPS1		Initialization         : FIPS-140-2 Level-2		HSM Serial Number      : 238180016		Firmware Version       : 4.3.0		Total Flash Memory     : 1900428		Free Flash Memory      : 1899720		Total SRAM Memory      : 26210216		Free SRAM Memory       : 17857232 

##update ssl fips

Updates the FIPS firmware. Note: Upgrade with compatible firmware is required. You must specify a valid file path and name


##Synopsys

update ssl fips -fipsFW &lt;string>


##Arguments

<b>fipsFW</b>
Path to the FIPS firmware file.



##Example

update ssl fips -fipsFW /var/nsinstall/fips/CN16XX-NFBE-FW-2.2-130001

