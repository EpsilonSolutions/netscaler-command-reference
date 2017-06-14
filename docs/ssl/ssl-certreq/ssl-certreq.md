#ssl certReq

The following operations can be performed on "ssl certReq":


##create ssl certReq

Generates a new Certificate Signing Request (CSR). A CSR is a collection of information including the domain name, company details, and the private key to be used to create the certificate.  Send the CSR to a Certificate Authority (CA) to obtain an X509 certificate for the user domain (web site).


##Synopsys

create ssl certReq &lt;reqFile> (-keyFile &lt;input_filename> | -fipsKeyName &lt;string>) [-keyform ( DER | PEM )  {-PEMPassPhrase }] -countryName &lt;string> -stateName &lt;string> -organizationName &lt;string> [-organizationUnitName &lt;string>] [-localityName &lt;string>] [-commonName &lt;string>] [-emailAddress &lt;string>] {-challengePassword } [-companyName &lt;string>]


##Arguments

<b>reqFile</b>
Name for and, optionally, path to the certificate signing request (CSR). /nsconfig/ssl/ is the default path.
Maximum value: 63

<b>keyFile</b>
Name of and, optionally, path to the private key used to create the certificate signing request, which then becomes part of the certificate-key pair. The private key can be either an RSA or a DSA key. The key must be present in the appliance's local storage. /nsconfig/ssl is the default path.
Maximum value: 63

<b>fipsKeyName</b>
Name of the FIPS key used to create the certificate signing request. FIPS keys are created inside the Hardware Security Module of the FIPS card.

<b>keyform</b>
Format in which the key is stored on the appliance.
Possible values: DER, PEM
Default value: FORMAT_PEM

<b>countryName</b>
Two letter ISO code for your country. For example, US for United States.

<b>stateName</b>
Full name of the state or province where your organization is located. 
Do not abbreviate.

<b>organizationName</b>
Name of the organization that will use this certificate. The organization name (corporation, limited partnership, university, or government agency) must be registered with some authority at the national, state, or city level. Use the legal name under which the organization is registered. 
Do not abbreviate the organization name and do not use the following characters in the name: 
Angle brackets (&lt; &gt;) tilde (~), exclamation mark, at (@), pound (#), zero (0), caret (^), asterisk (*), forward slash (/), square brackets ([ ]), question mark (?).

<b>organizationUnitName</b>
Name of the division or section in the organization that will use the certificate.

<b>localityName</b>
Name of the city or town in which your organization's head office is located.

<b>commonName</b>
Fully qualified domain name for the company or web site. The common name must match the name used by DNS servers to do a DNS lookup of your server. Most browsers use this information for authenticating the server's certificate during the SSL handshake. If the server name in the URL does not match the common name as given in the server certificate, the browser terminates the SSL handshake or prompts the user with a warning message. 
Do not use wildcard characters, such as asterisk (*) or question mark (?), and do not use an IP address as the common name. The common name must not contain the protocol specifier &lt;http://&gt; or &lt;https://&gt;.

<b>emailAddress</b>
Contact person's e-mail address. This address is publically displayed as part of the certificate. Provide an e-mail address that is monitored by an administrator who can be contacted about the certificate.

<b>challengePassword</b>
Pass phrase, embedded in the certificate signing request that is shared only between the client or server requesting the certificate and the SSL certificate issuer (typically the certificate authority). This pass phrase can be used to authenticate a client or server that is requesting a certificate from the certificate authority.

<b>companyName</b>
Additional name for the company or web site.



##Example

create ssl certreq /nsconfig/ssl/csr.pem -keyFile /nsconfig/ssl/rsa1024.pem 

##Related Commands

<ul><li><a href="../../../-ssl/-ssl">create ssl cert</a></li><li><a href="../../../te-ssl-r/te-ssl-r">create ssl rsakey</a></li><li><a href="../../../te-ssl-d/te-ssl-d">create ssl dsakey</a></li></ul>



