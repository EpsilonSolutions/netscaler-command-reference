#aaa kcdAccount

The following operations can be performed on "aaa kcdAccount":


[add](#add-aaa-kcdaccount) | [rm](#rm-aaa-kcdaccount) | [set](#set-aaa-kcdaccount) | [unset](#unset-aaa-kcdaccount) | [show](#show-aaa-kcdaccount)

##add aaa kcdAccount

Add a Kerberos constrained delegation account.


##Synopsys

add aaa kcdAccount &lt;kcdAccount> {-keytab &lt;string>} {-realmStr &lt;string>} {-delegatedUser &lt;string>} {-kcdPassword } {-usercert &lt;string>} {-cacert &lt;string>} [-userRealm &lt;string>] [-enterpriseRealm &lt;string>] [-serviceSPN &lt;string>]


##Arguments

<b>kcdAccount</b>
The name of the KCD account.

<b>keytab</b>
The path to the keytab file. If specified other parameters in this command need not be given

<b>realmStr</b>
Kerberos Realm.

<b>delegatedUser</b>
Username that can perform kerberos constrained delegation.

<b>kcdPassword</b>
Password for Delegated User.

<b>usercert</b>
SSL Cert (including private key) for Delegated User.

<b>cacert</b>
CA Cert for UserCert or when doing PKINIT backchannel.

<b>userRealm</b>
Realm of the user

<b>enterpriseRealm</b>
Enterprise Realm of the user. This should be given only in certain KDC deployments where KDC expects Enterprise username instead of Principal Name

<b>serviceSPN</b>
Service SPN. When specified, this will be used to fetch kerberos tickets. If not specified, Netscaler will construct SPN using service fqdn



##Example

add aaa kcdaccount my_kcd_acct -keytab /var/mykcd.keytabadd aaa kcdaccount my_kcd_acct -keytabThe above example adds a Kerberos constrained delegation account my_kcd_acct, with the keytab file located at /var/mykcd.keytab

##rm aaa kcdAccount

Remove the KCD account.


##Synopsys

rm aaa kcdAccount &lt;kcdAccount>


##Arguments

<b>kcdAccount</b>
The KCD account name.



##set aaa kcdAccount

Set the KCD account information.


##Synopsys

set aaa kcdAccount &lt;kcdAccount> [-keytab &lt;string>] [-realmStr &lt;string>] [-delegatedUser &lt;string>] [-kcdPassword ] [-usercert &lt;string>] [-cacert &lt;string>] [-userRealm &lt;string>] [-enterpriseRealm &lt;string>] [-serviceSPN &lt;string>]


##Arguments

<b>kcdAccount</b>
The name of the KCD account.

<b>keytab</b>
The path to the keytab file. If specified other parameters in this command need not be given

<b>realmStr</b>
Kerberos Realm.

<b>delegatedUser</b>
Username that can perform kerberos constrained delegation.

<b>kcdPassword</b>
Password for Delegated User.

<b>usercert</b>
SSL Cert (including private key) for Delegated User.

<b>cacert</b>
CA Cert for UserCert or when doing PKINIT backchannel.

<b>userRealm</b>
Realm of the user

<b>enterpriseRealm</b>
Enterprise Realm of the user. This should be given only in certain KDC deployments where KDC expects Enterprise username instead of Principal Name

<b>serviceSPN</b>
Service SPN. When specified, this will be used to fetch kerberos tickets. If not specified, Netscaler will construct SPN using service fqdn



##Example

set aaa kcdaccount my_kcd_acct -keytab /var/hiskcd.keytabThe above command sets the keytab location for KCD account my_kcd_acct to /var/hiskcd.keytab

##unset aaa kcdAccount

Unset the KCD account information..Refer to the set aaa kcdAccount command for meanings of the arguments.


##Synopsys

unset aaa kcdAccount &lt;kcdAccount> [-usercert] [-cacert] [-userRealm] [-enterpriseRealm] [-serviceSPN]


##show aaa kcdAccount

Display KCD accounts.


##Synopsys

show aaa kcdAccount [&lt;kcdAccount>]


##Arguments

<b>kcdAccount</b>
The KCD account name.



##Outputs

<b>keytab</b>
The path to the keytab file. If specified other parameters in this command need not be given

<b>principle</b>
SPN extracted from keytab file.

<b>kcdSPN</b>
Host SPN extracted from keytab file.

<b>realmStr</b>
Kerberos Realm.

<b>delegatedUser</b>
Username that can perform kerberos constrained delegation.

<b>kcdPassword</b>
Password for Delegated User.

<b>usercert</b>
SSL Cert (including private key) for Delegated User.

<b>cacert</b>
CA Cert for UserCert or when doing PKINIT backchannel.

<b>userRealm</b>
Realm of the user

<b>enterpriseRealm</b>
Enterprise Realm of the user. This should be given only in certain KDC deployments where KDC expects Enterprise username instead of Principal Name

<b>serviceSPN</b>
Service SPN. When specified, this will be used to fetch kerberos tickets. If not specified, Netscaler will construct SPN using service fqdn

<b>stateflag</b>

<b>devno</b>

<b>count</b>



##Example

Example&gt; show aaa kcdaccount my_kcd_acct        KcdAccount: my_kcd_acct           Keytab: /var/mykcd.keytab Done&gt;

