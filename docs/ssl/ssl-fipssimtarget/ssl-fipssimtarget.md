#ssl fipsSIMTarget

The following operations can be performed on "ssl fipsSIMTarget":


[enable](#enable-ssl-fipssimtarget) | [init](#init-ssl-fipssimtarget)

##enable ssl fipsSIMTarget

Enables secure transfer of FIPS keys in a high availability setup from the primary appliance to the secondary appliance.


##Synopsys

enable ssl fipsSIMTarget &lt;keyVector> &lt;sourceSecret>


##Arguments

<b>keyVector</b>
Name of and, optionally, path to the target FIPS appliance's key vector. /nsconfig/ssl/ is the default path.

<b>sourceSecret</b>
Name of and, optionally, path to the source FIPS appliance's secret data. /nsconfig/ssl/ is the default path.



##Example

enable fipsSIMtarget /nsconfig/ssl/target.key /nsconfig/ssl/source.secret

##init ssl fipsSIMTarget

Initialize the target (secondary) FIPS appliance for participating in a secure exchange of keys with the primary FIPS appliance.


##Synopsys

init ssl fipsSIMTarget &lt;certFile> &lt;keyVector> &lt;targetSecret>


##Arguments

<b>certFile</b>
Name of and, optionally, path to the source FIPS appliance's certificate file. /nsconfig/ssl/ is the default path.

<b>keyVector</b>
Name for and, optionally, path to the target FIPS appliance's key vector. /nsconfig/ssl/ is the default path.

<b>targetSecret</b>
Name for and, optionally, path to the target FIPS appliance's secret data. The default input path for the secret data is /nsconfig/ssl/.



##Example

init fipsSIMtarget /nsconfig/ssl/source.cert /nsconfig/ssl/target.key /nsconfig/ssl/target.secret

