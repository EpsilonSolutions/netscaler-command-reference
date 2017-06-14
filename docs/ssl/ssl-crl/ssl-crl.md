#ssl crl

The following operations can be performed on "ssl crl":


[add](#add-ssl-crl) | [create](#create-ssl-crl) | [rm](#rm-ssl-crl) | [set](#set-ssl-crl) | [unset](#unset-ssl-crl) | [show](#show-ssl-crl)

##add ssl crl

Adds a Certificate Revocation List (CRL). A CRL identifies invalid certificates by serial number and issuer. In a high availability configuration, the CRL must be in the same location on the primary and secondary nodes.


##Synopsys

add ssl crl &lt;crlName> &lt;crlPath> [-inform ( DER | PEM )] [-refresh ( ENABLED | DISABLED )] [-CAcert &lt;string>] [-method ( HTTP | LDAP )] [-server &lt;ip_addr|ipv6_addr|*> | -url &lt;URL>] [-port &lt;port>] [-baseDN &lt;string>] [-scope ( Base | One )] [-interval &lt;interval>] [-day &lt;integer>] [-time &lt;HH:MM>] [-bindDN &lt;string>] {-password } [-binary ( YES | NO )]


##Arguments

<b>crlName</b>
Name for the Certificate Revocation List (CRL). Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the CRL is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my crl" or 'my crl').

<b>crlPath</b>
Path to the CRL file. /var/netscaler/ssl/ is the default path.

<b>inform</b>
Input format of the CRL file. The two formats supported on the appliance are:
PEM - Privacy Enhanced Mail.
DER - Distinguished Encoding Rule.
Possible values: DER, PEM
Default value: FORMAT_PEM

<b>refresh</b>
Set CRL auto refresh.
Possible values: ENABLED, DISABLED

<b>CAcert</b>
CA certificate that has issued the CRL. Required if CRL Auto Refresh is selected. Install the CA certificate on the appliance before adding the CRL.

<b>method</b>
Method for CRL refresh. If LDAP is selected, specify the method, CA certificate, base DN, port, and LDAP server name. If HTTP is selected, specify the CA certificate, method, URL, and port. Cannot be changed after a CRL is added.
Possible values: HTTP, LDAP

<b>server</b>
IP address of the LDAP server from which to fetch the CRLs.

<b>url</b>
URL of the CRL distribution point.

<b>port</b>
Port for the LDAP server.
Minimum value: 1

<b>baseDN</b>
Base distinguished name (DN), which is used in an LDAP search to search for a CRL. Citrix recommends searching for the Base DN instead of the Issuer Name from the CA certificate, because the Issuer Name field might not exactly match the LDAP directory structure's DN.

<b>scope</b>
Extent of the search operation on the LDAP server. Available settings function as follows:
One - One level below Base DN.
Base - Exactly the same level as Base DN.
Possible values: Base, One
Default value: NSAPI_ONESCOPE

<b>interval</b>
CRL refresh interval. Use the NONE setting to unset this parameter.
Possible values: MONTHLY, WEEKLY, DAILY, NONE

<b>day</b>
Day on which to refresh the CRL, or, if the Interval parameter is not set, the number of days after which to refresh the CRL. If Interval is set to MONTHLY, specify the date. If Interval is set to WEEKLY, specify the day of the week (for example, Sun=0 and Sat=6). This parameter is not applicable if the Interval is set to DAILY.
Maximum value: 31

<b>time</b>
Time, in hours (1-24) and minutes (1-60), at which to refresh the CRL.

<b>bindDN</b>
Bind distinguished name (DN) to be used to access the CRL object in the LDAP repository if access to the LDAP repository is restricted or anonymous access is not allowed.

<b>password</b>
Password to access the CRL in the LDAP repository if access to the LDAP repository is restricted or anonymous access is not allowed.

<b>binary</b>
Set the LDAP-based CRL retrieval mode to binary.
Possible values: YES, NO
Default value: NO



##Example

1)	add ssl certkey CAcert -cert /nsconfig/ssl/ca_cert.pemadd ssl crl crl_file /var/netscaler/ssl/crl.pem -cacert CAcertThe above command adds a CRL from local storage system (HDD) with no refresh set.2)	add ssl certkey CAcert -cert /nsconfig/ssl/ca_cert.pemadd ssl crl crl_file /var/netscaler/ssl/crl_new.pem -cacert Cacert -refresh ENABLED -server 10.102.1.100 -port 389 -interval DAILY -baseDN o=example.com,ou=security,c=USThe above command adds a CRL to the system by fetching the CRL from the LDAP server and setting the refresh interval as daily.

##create ssl crl

Revokes a certificate, or list of certificates, or generates a CRL for the list of revoked certificates.


##Synopsys

create ssl crl &lt;CAcertFile> &lt;CAkeyFile> &lt;indexFile> (-revoke &lt;input_filename> | -genCRL &lt;output_filename>) {-password }


##Arguments

<b>CAcertFile</b>
Name of and, optionally, path to the CA certificate file.
/nsconfig/ssl/ is the default path.
Maximum value: 63

<b>CAkeyFile</b>
Name of and, optionally, path to the CA key file. /nsconfig/ssl/ is the default path
Maximum value: 63

<b>indexFile</b>
Name of and, optionally, path to the file containing the serial numbers of all the certificates that are revoked. Revoked certificates are appended to the file. /nsconfig/ssl/ is the default path
Maximum value: 63

<b>revoke</b>
Name of and, optionally, path to the certificate to be revoked. /nsconfig/ssl/ is the default path.
Maximum value: 63

<b>genCRL</b>
Name of and, optionally, path to the CRL file to be generated. The list of certificates that have been revoked is obtained from the index file. /nsconfig/ssl/ is the default path.
Maximum value: 63

<b>password</b>
Password for the CA key file.
Maximum value: 31



##Example

1)	create crl /nsconfig/ssl/cacert.pem /nsconfig/ssl/cakey.pem /nsconfig/ssl/index.txt -gencrl /var/netscaler/ssl/crl.pem

##rm ssl crl

Removes the specified CRL from the appliance.


##Synopsys

rm ssl crl &lt;crlName> ...


##Arguments

<b>crlName</b>
Name of the CRL to remove.



##Example

1)	rm ssl crl ca_crlThe above CLI command to delete the CRL object ca_crl from the system is.

##set ssl crl

Modifies all the parameters of a CRL, except the CRL name and method.


##Synopsys

set ssl crl &lt;crlName> [-refresh ( ENABLED | DISABLED )] [-CAcert &lt;string>] [-server &lt;ip_addr|ipv6_addr|*> | -url &lt;URL>] [-method ( HTTP | LDAP )] [-port &lt;port>] [-baseDN &lt;string>] [-scope ( Base | One )] [-interval &lt;interval>] [-day &lt;integer>] [-time &lt;HH:MM>] [-bindDN &lt;string>] {-password } [-binary ( YES | NO )]


##Arguments

<b>crlName</b>
Name of the CRL to be modified.

<b>refresh</b>
Set CRL auto refresh.
Possible values: ENABLED, DISABLED

<b>CAcert</b>
CA certificate that has issued the CRL. Required if CRL Auto Refresh is selected. Install the CA certificate on the appliance before adding the CRL.

<b>server</b>
IP address of the LDAP server from which to fetch the CRLs.

<b>method</b>
Method for CRL refresh. If LDAP is selected, specify the method, CA certificate, base DN, port, and LDAP server name. If HTTP is selected, specify the CA certificate, method, URL, and port. Cannot be changed after a CRL is added.
Possible values: HTTP, LDAP

<b>port</b>
Port for the LDAP server.
Minimum value: 1

<b>baseDN</b>
Base distinguished name (DN), which is used in an LDAP search to search for a CRL. Citrix recommends searching for the Base DN instead of the Issuer Name from the CA certificate, because the Issuer Name field might not exactly match the LDAP directory structure's DN.

<b>scope</b>
Extent of the search operation on the LDAP server. Available settings function as follows:
One - One level below Base DN.
Base - Exactly the same level as Base DN.
Possible values: Base, One
Default value: NSAPI_ONESCOPE

<b>interval</b>
CRL refresh interval. Use the NONE setting to unset this parameter.
Possible values: MONTHLY, WEEKLY, DAILY, NOW, NONE

<b>day</b>
Day on which to refresh the CRL, or, if the Interval parameter is not set, the number of days after which to refresh the CRL. If Interval is set to MONTHLY, specify the date. If Interval is set to WEEKLY, specify the day of the week (for example, Sun=0 and Sat=6). This parameter is not applicable if the Interval is set to DAILY.
Maximum value: 31

<b>time</b>
Time, in hours (1-24) and minutes (1-60), at which to refresh the CRL.

<b>bindDN</b>
Bind distinguished name (DN) to be used to access the CRL object in the LDAP repository if access to the LDAP repository is restricted or anonymous access is not allowed.

<b>password</b>
Password to access the CRL in the LDAP repository if access to the LDAP repository is restricted or anonymous access is not allowed.

<b>binary</b>
Set the LDAP-based CRL retrieval mode to binary.
Possible values: YES, NO
Default value: NO



##Example

1)	set ssl crl crl_file -refresh ENABLE -interval MONTHLY -days 10 -time 12:00The above example sets the CRL refresh to every Month, on date=10, and time=12:00hrs.2)	set ssl crl crl_file -refresh ENABLE -interval WEEKLY -days 1 -time 00:10The above example sets the CRL refresh every Week, on weekday=Monday, and at time 10 past midnight.3)	set ssl crl crl_file -refresh ENABLE -interval DAILY -days 1 -time 12:00The above example sets the CRL refresh every Day, at 12:00hrs.4)	set ssl crl crl_file -refresh ENABLE -days 10The above example sets the CRL refresh after every 10 days.Note: The CRL will be refreshed after every 10 days. The time for CRL refresh will be 00:00 hrs.5)	set ssl crl crl_file -refresh ENABLE -time 01:00The above example sets the CRL refresh after every 1 hour.6)	set ssl crl crl_file -refresh ENABLE -interval NOWThe above example sets the CRL refresh instantaneously.

##unset ssl crl

Use this command to remove ssl crl settings.Refer to the set ssl crl command for meanings of the arguments.


##Synopsys

unset ssl crl &lt;crlName> [-refresh] [-CAcert] [-server] [-method] [-url] [-port] [-baseDN] [-scope] [-interval] [-day] [-time] [-bindDN] [-password] [-binary]


##show ssl crl

Displays information about all the CRLs configured on the appliance, or displays detailed information about the specified CRL.


##Synopsys

show ssl crl [&lt;crlName>]


##Arguments

<b>crlName</b>
Name of the CRL for which to show detailed information.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>crlPath</b>
The name and path to the file containing the CRL.

<b>inform</b>
The encoding format of the CRL (PEM or DER).

<b>CAcert</b>
The CA certificate that issued the CRL.

<b>refresh</b>
The state of the auto refresh feature for the CRL.

<b>scope</b>
Extent of the search operation on the LDAP server.
                   Base: Exactly the same level as basedn
                   One : One level below basedn.

<b>server</b>
The IP address of the LDAP/HTTP server from which the CRLs are to be fetched.

<b>port</b>
The port of the LDAP/HTTP server.

<b>url</b>
URL of the CRL distribution point.

<b>method</b>
The method for CRL refresh (LDAP or HTTP).

<b>baseDN</b>
The baseDN to be used to fetch the CRL object from the LDAP server.

<b>interval</b>
The CRL refresh interval.

<b>day</b>
The day when the CRL is to be refreshed.

<b>time</b>
The time when the CRL is to be refreshed.

<b>bindDN</b>
The  bindDN  to  be  used  to  access the CRL object in the LDAP repository.

<b>password</b>
The password to be is used to access the CRL object in the  LDAP repository.

<b>flags</b>
CRL status flag.

<b>lastupdatetime</b>
Last CRL refresh time.

<b>version</b>
CRL version.

<b>signaturealgo</b>
Signature algorithm.

<b>issuer</b>
Issuer name.

<b>lastupdate</b>
Last update time.

<b>nextupdate</b>
Next update time.

<b>date</b>
Certificate Revocation date

<b>number</b>
Certificate Serial number.

<b>binary</b>
Mode of retrieval of CRL from LDAP server.

<b>daysToExpiration</b>
Number of days remaining for the CRL to expire.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

1) An example output of the show ssl crl command is as follows:1 configured CRL(s)1 Name: ca_crlCRL Path: /var/netscaler/ssl/cr1.derFormat: DER Cacert: ca_certRefresh: DISABLED2) An example of the output of the show ssl crl ca_crl command is as follows:Name: ca_crl Status: Valid, Days to expiration: 21CRL Path: /var/netscaler/ssl/cr1.derFormat: DER	CAcert: ca_certRefresh: DISABLEDVersion: 1Signature Algorithm: md5WithRSAEncryptionIssuer: /C=US/ST=CA/L=santa clara /O=CA/OU=securityLast_update:Dec 21 09:47:16 2001 GMTNext_update:Jan 20 09:47:16 2002 GMTRevoked Certificates:	Serial Number: 01	Revocation Date:Dec 21 09:47:02 2001 GMT	Serial Number: 02	Revocation Date:Dec 21 09:47:02 2001 GMT

