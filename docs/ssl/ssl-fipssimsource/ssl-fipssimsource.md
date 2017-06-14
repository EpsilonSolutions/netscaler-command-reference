#ssl fipsSIMSource

The following operations can be performed on "ssl fipsSIMSource":


[enable](#enable-ssl-fipssimsource) | [init](#init-ssl-fipssimsource)

##enable ssl fipsSIMSource

Enable the source FIPS appliance to participate in a secure exchange of keys with the target (secondary) FIPS appliance.


##Synopsys

enable ssl fipsSIMSource &lt;targetSecret> &lt;sourceSecret>


##Arguments

<b>targetSecret</b>
Name of and, optionally, path to the target FIPS appliance's secret data. /nsconfig/ssl/ is the default path.

<b>sourceSecret</b>
Name for and, optionally, path to the source FIPS appliance's secret data. /nsconfig/ssl/ is the default path.



##Example

enable fipsSIMsource /nsconfig/ssl/target.secret /nsconfig/ssl/source.secret

##init ssl fipsSIMSource

Initialize the source FIPS appliance for participating in a secure exchange of keys with the target (secondary) FIPS appliance.


##Synopsys

init ssl fipsSIMSource &lt;certFile>


##Arguments

<b>certFile</b>
Name for and, optionally, path to the source FIPS appliance's certificate file. /nsconfig/ssl/ is the default path.



##Example

init fipsSIMsource /nsconfig/ssl/source.cert

