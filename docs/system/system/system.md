#system

The following operations can be performed on "system":


##stat system

This command displays  system statistics


##Synopsys

stat system [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>Maximum Memory Available (MB) (MemTotAvail)</b>
Total system memory available for PE to grab from the system.

<b>-12.0 V Supply Voltage (V12n)</b>
Power supply -12V output. Acceptable range is -13.20 through -10.80 volts. 9800 and 9960 platforms display standard value of -12.0V.

<b>-5.0 V Supply Voltage (V50n)</b>
Power supply -5V output. Acceptable range is -5.50 through -4.50 volts. 9800 and 9960 platforms display standard value of -5.0V.

<b>CPU usage (CPU)</b>
CPU utilization: percentage * 10.

<b>Average CPU usage (CPU)</b>
Shows average CPU utilization percentage if more than 1 CPU is present.

<b>CPU1</b>
CPU 1 (currently the slave CPU) utilization, as percentage of capacity. Not applicable for a single-CPU system.

<b>CPU0</b>
CPU 0 (currently the master CPU) utilization, as percentage of capacity.

<b>Voltage 7 (Volts) (volt7)</b>
Voltage of a device connected to health monitoring chip through pin 7.

<b>Voltage 6 (Volts) (volt6)</b>
Voltage of a device connected to health monitoring chip through pin 6.

<b>Voltage 5 (Volts) (volt5)</b>
Voltage of a device connected to health monitoring chip through pin 5.

<b>Voltage 4 (Volts) (volt4)</b>
Voltage of a device connected to health monitoring chip through pin 4.

<b>Voltage 3 (Volts) (volt3)</b>
Voltage of a device connected to health monitoring chip through pin 3.

<b>Voltage 2 (Volts) (volt2)</b>
Voltage of a device connected to health monitoring chip through pin 2.

<b>Voltage 1 (Volts) (volt1)</b>
Voltage of a device connected to health monitoring chip through pin 1.

<b>Voltage 0 (Volts) (volt0)</b>
Voltage of a device connected to health monitoring chip through pin 0.

<b>Voltage Sensor2(Volts)  (VSEN2)</b>
Voltage Sensor 2 Input. Currently only 13k Platforms will have valid value for this counter and for older platforms this will be 0.

<b>5V Standby Voltage(Volts)  (V5SB)</b>
Power Supply 5V Standby Voltage. Currently only 13k Platforms will have valid value for this counter and for older platforms this will be 0.

<b>Intel CPU Vtt Power(Volts)  (VTT)</b>
Intel CPU Vtt power. Currently only 13k Platforms will have valid value for this counter and for older platforms this will be 0.

<b>Battery Voltage (Volts)  (VBAT)</b>
Onboard battery power supply output. 9800 and 9950 platforms display standard value of 5.0V.

<b>+12.0 V Supply Voltage (V+12)</b>
Power supply +12V output. Acceptable range is 10.80 through 13.20 volts.

<b>+5.0 V Supply Voltage (V50)</b>
Power supply +5V output. Acceptable range is 4.50 through 5.50 volts.

<b>Standby 3.3 V Supply Voltage (V33Stby)</b>
Standby power supply +3.3V output. Acceptable range is 2.970 through 3.630 volts. 9800 and 9960 platforms display standard value of 3.3V.
You can configure Standby 3.3V Supply Voltage by using the Set snmp alarm VOLTAGE-LOW command to set the lower limit and the Set snmp alarm VOLTAGE-HIGH command to set the upper limit.

<b>Main 3.3 V Supply Voltage (V33Main)</b>
Main power supply +3.3V output. Acceptable range is 2.970 through 3.630 volts. This is a critical counter.
You can configure Main 3.3V Supply Voltage, by using the Set snmp alarm VOLTAGE-LOW command to set the lower limit and the Set snmp alarm VOLTAGE-HIGH command to set the upper limit.

<b>CPU 1 Core Voltage (Volts) (VCC1)</b>
CPU core 1 voltage. Acceptable range is 1.080 through 1.650 volts. If CPU 1 is not connected to the health monitoring chip, display shows voltage of CPU 0.

<b>CPU 0 Core Voltage (Volts) (VCC0)</b>
CPU core 0 voltage. Acceptable range is 1.080 through 1.650 volts.

<b>Number of CPUs (CPUs)</b>
The number of CPUs on the NetScaler appliance.

<b>InUse Memory (%) (MemUsage)</b>
Percentage of memory utilization on NetScaler.

<b>Memory usage (MB) (MemUseMB)</b>
Main memory currently in use, in megabytes.

<b>Management CPU usage (%) (CPU)</b>
Management CPU utilization percentage.

<b>Packet CPU usage (%) (CPU)</b>
Average CPU utilization percentage for all packet engines excluding management PE.

<b>CPU usage (%) (CPU)</b>
CPU utilization percentage.

<b>Average CPU usage (%) (CPU)</b>
Average CPU utilization percentage. Not applicable for a single-CPU system.

<b>Up since (Since)</b>
Time when the NetScaler appliance was last started.

<b>/flash Used (%) (disk0PerUsage)</b>
Used space in /flash partition of the disk, as a percentage. This is a critical counter.
You can configure /flash Used (%) by using the Set snmp alarm DISK-USAGE-HIGH command.

<b>/var Used (%) (disk1PerUsage)</b>
Used space in /var partition of the disk, as a percentage. This is a critical counter. You can configure /var Used (%) by using the Set snmp alarm DISK-USAGE-HIGH command.

<b>CPU Fan 0 Speed (RPM) (CPUFan0)</b>
CPU Fan 0 speed. Acceptable range is 3000 through 6000 RPM. This is a critical counter.
You can configure CPU Fan 0 Speed by using the Set snmp alarm FAN-SPEED-LOW command to set the lower limit.

<b>CPU Fan 1 Speed (RPM) (CPUFan1)</b>
CPU Fan 1 speed. Acceptable range is 3000 through 6000 RPM. 7000 platform displays speed of CPU fan 0. This is a critical counter.
You can configure CPU Fan 1 Speed by using the Set snmp alarm FAN-SPEED-LOW command to set the lower limit.

<b>System Fan Speed (RPM) (systemFan)</b>
System fan speed. Acceptable range is 3000 through 6000 RPM. This is a critical counter.
You can configure System Fan Speed by using the Set snmp alarm FAN-SPEED-LOW command to set the lower limit.

<b>System Fan 1 Speed (RPM) (systemFan1)</b>
System fan 1 speed. For new platforms associated pin is connected to CPU supporting fans. For platforms in which it is not connected, it will point to System Fan.

<b>System Fan 2 Speed (RPM) (systemFan2)</b>
System fan 2 speed. For new platforms associated pin is connected to CPU supporting fans. For platforms in which it is not connected, it will point to System Fan

<b>CPU 0 Temperature (Celsius) (TCPU0)</b>
CPU 0 temperature. 9800 and 9960 platforms display internal chip temperature. This is a critical counter.
You can configure CPU 0 Temperature by using the Set snmp alarm TEMPERATURE-HIGH command to set the upper limit.

<b>CPU 1 Temperature (Celsius) (TCPU1)</b>
CPU 1 temperature. 9800 and 9960 platforms display internal chip temperature. 7000, 9010 and 10010 platforms display CPU 0 temperature. This is a critical counter.
You can configure CPU 1 Temperature by using the Set snmp alarm TEMPERATURE-HIGH command to set the upper limit.

<b>Internal Temperature (Celsius) (intTemp)</b>
Internal temperature of health monitoring chip. This is a critical counter.
You can configure Internal Temperature by using the Set snmp alarm TEMPERATURE-HIGH command to set the upper limit.

<b>Power supply 1 status (PS1FAIL)</b>
Power supply 1 failure status.

<b>Power supply 2 status (PS2FAIL)</b>
Power supply 2 failure status.

<b>/flash Size (MB) (disk0Size)</b>
Size of /flash partition of the hard disk.

<b>/flash Used (MB) (disk0Used)</b>
Used space in /flash partition of the hard disk.

<b>/flash Available (MB) (disk0Avail)</b>
Available space in /flash partition of the hard disk.

<b>/var Size (MB) (disk1Size)</b>
Size of /var partition of the hard disk.

<b>/var Used (MB) (disk1Used)</b>
Used space in /var partition of the hard disk.

<b>/var Available (MB) (disk1Avail)</b>
Available space in /var partition of the hard disk.

<b>Fan 0 Speed (RPM) (Fan0)</b>
Speed of Fan 0 if associated pin is connected to health monitoring chip.

<b>Fan 1 Speed (RPM) (Fan1)</b>
Speed of Fan 1 if associated pin is connected to health monitoring chip.

<b>Fan 2 Speed (RPM) (Fan2)</b>
Speed of Fan 2 if associated pin is connected to health monitoring chip.

<b>Fan 3 Speed (RPM) (Fan3)</b>
Speed of Fan 3 if associated pin is connected to health monitoring chip.

<b>Temperature 0 (Celsius) (temp0)</b>
Temperature of a device connected to health monitoring chip through pin 0.

<b>Temperature 1 (Celsius) (temp1)</b>
Temperature of a device connected to health monitoring chip through pin 1.

<b>Temperature 2 (Celsius) (temp2)</b>
Temperature of a device connected to health monitoring chip through pin 2.

<b>Temperature 3 (Celsius) (temp3)</b>
Temperature of a device connected to health monitoring chip through pin 3.

<b>Power supply 3 status (PS3FAIL)</b>
Power supply 3 failure status.

<b>Power supply 4 status (PS4FAIL)</b>
Power supply 4 failure status.

<b>Up time (UP)</b>
Seconds since the NetScaler appliance started.

<b>System memory (MB) (Memory)</b>
Total amount of system memory, in megabytes.

<b>Management CPU usage (CPU)</b>
Management CPU utilization: percentage * 10.

<b>Master CPU usage (CPU0)</b>
CPU0 utilization: percentage * 10.

<b>Slave CPU usage (CPU1)</b>
CPU1 utilization, percentage * 10.



##Related Commands

<ul><li><a href="../../../at-syst/at-syst">stat system bw</a></li><li><a href="../../../tat-syste/tat-syste">stat system cpu</a></li><li><a href="../../../l#stat-system-m/l#stat-system-m">stat system memory</a></li></ul>



