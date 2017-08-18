#ipsecalg profile

The following operations can be performed on "ipsecalg profile":


[add](#add-ipsecalg-profile) | [set](#set-ipsecalg-profile) | [unset](#unset-ipsecalg-profile) | [show](#show-ipsecalg-profile) | [rm](#rm-ipsecalg-profile)

##add ipsecalg profile

Add an ipsec alg profile.


##Synopsys

add ipsecalg profile &lt;name> [-ikeSessionTimeout &lt;positive_integer>] [-espSessionTimeout &lt;positive_integer>] [-espGateTimeout &lt;positive_integer>] [-connfailover ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
The name of the ipsec alg profile

<b>ikeSessionTimeout</b>
IKE session timeout in minutes
Default value: 60
Minimum value: 1
Maximum value: 1440

<b>espSessionTimeout</b>
ESP session timeout in minutes.
Default value: 60
Minimum value: 1
Maximum value: 1440

<b>espGateTimeout</b>
Timeout ESP in seconds as no ESP packets are seen after IKE negotiation
Default value: 60
Minimum value: 30
Maximum value: 1200

<b>connfailover</b>
Mode in which the connection failover feature must operate for the IPSec Alg. After a failover, established UDP connections and ESP packet flows are kept active and resumed on the secondary appliance. Recomended setting is ENABLED.
Possible values: ENABLED, DISABLED
Default value: ENABLED



##set ipsecalg profile

Set an ipsec alg profile parameter.


##Synopsys

set ipsecalg profile &lt;name> [-ikeSessionTimeout &lt;positive_integer>] [-espSessionTimeout &lt;positive_integer>] [-espGateTimeout &lt;positive_integer>] [-connfailover ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
The name of the ipsec alg profile

<b>ikeSessionTimeout</b>
IKE session timeout in minutes
Default value: 60
Minimum value: 1
Maximum value: 1440

<b>espSessionTimeout</b>
ESP session timeout in minutes.
Default value: 60
Minimum value: 1
Maximum value: 1440

<b>espGateTimeout</b>
Timeout ESP in seconds as no ESP packets are seen after IKE negotiation
Default value: 60
Minimum value: 30
Maximum value: 1200

<b>connfailover</b>
Mode in which the connection failover feature must operate for the IPSec Alg. After a failover, established UDP connections and ESP packet flows are kept active and resumed on the secondary appliance. Recomended setting is ENABLED.
Possible values: ENABLED, DISABLED
Default value: ENABLED



##unset ipsecalg profile

Use this command to remove ipsecalg profile settings.Refer to the set ipsecalg profile command for meanings of the arguments.


##Synopsys

unset ipsecalg profile &lt;name> [-ikeSessionTimeout] [-espSessionTimeout] [-espGateTimeout] [-connfailover]


##show ipsecalg profile

Display all of the configured ipsec alg profiles


##Synopsys

show ipsecalg profile [&lt;name>]


##Arguments

<b>name</b>
The name of the ipsec alg profile



##Outputs

<b>ikeSessionTimeout</b>
IKE session timeout in minutes

<b>espSessionTimeout</b>
ESP session timeout in minutes.

<b>espGateTimeout</b>
Timeout ESP in seconds as no ESP packets are seen after IKE negotiation

<b>connfailover</b>
Mode in which the connection failover feature must operate for the IPSec Alg. After a failover, established UDP connections and ESP packet flows are kept active and resumed on the secondary appliance. Recomended setting is ENABLED.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show ipsecalg profile

##rm ipsecalg profile

Remove an ipsec alg profile


##Synopsys

rm ipsecalg profile &lt;name>


##Arguments

<b>name</b>
The name of the ipsec alg profile.



##Example

rm ipsecalg profile 

