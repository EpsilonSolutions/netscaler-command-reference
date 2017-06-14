#appfw learningsettings

The following operations can be performed on "appfw learningsettings":


[set](#set-appfw-learningsettings) | [unset](#unset-appfw-learningsettings) | [show](#show-appfw-learningsettings)

##set appfw learningsettings

Configures the application firewall learning settings for the specified profile.


##Synopsys

set appfw learningsettings &lt;profileName> [-startURLMinThreshold &lt;positive_integer>] [-startURLPercentThreshold &lt;positive_integer>] [-cookieConsistencyMinThreshold &lt;positive_integer>] [-cookieConsistencyPercentThreshold &lt;positive_integer>] [-CSRFtagMinThreshold &lt;positive_integer>] [-CSRFtagPercentThreshold &lt;positive_integer>] [-fieldConsistencyMinThreshold &lt;positive_integer>] [-fieldConsistencyPercentThreshold &lt;positive_integer>] [-crossSiteScriptingMinThreshold &lt;positive_integer>] [-crossSiteScriptingPercentThreshold &lt;positive_integer>] [-SQLInjectionMinThreshold &lt;positive_integer>] [-SQLInjectionPercentThreshold &lt;positive_integer>] [-fieldFormatMinThreshold &lt;positive_integer>] [-fieldFormatPercentThreshold &lt;positive_integer>] [-XMLWSIMinThreshold &lt;positive_integer>] [-XMLWSIPercentThreshold &lt;positive_integer>] [-XMLAttachmentMinThreshold &lt;positive_integer>] [-XMLAttachmentPercentThreshold &lt;positive_integer>]


##Arguments

<b>profileName</b>
Name of the profile.

<b>startURLMinThreshold</b>
Minimum number of application firewall sessions that the learning engine must observe to learn start URLs.
Default value: AS_LEARNINGSETTINGS_DEFAULT_MINTHRESHOLD
Minimum value: 1

<b>startURLPercentThreshold</b>
Minimum percentage of application firewall sessions that must contain a particular start URL pattern for the learning engine to learn that start URL.
Default value: AS_LEARNINGSETTINGS_DEFAULT_PERCENTTHRESHOLD
Maximum value: 100

<b>cookieConsistencyMinThreshold</b>
Minimum number of application firewall sessions that the learning engine must observe to learn cookies.
Default value: AS_LEARNINGSETTINGS_DEFAULT_MINTHRESHOLD
Minimum value: 1

<b>cookieConsistencyPercentThreshold</b>
Minimum percentage of application firewall sessions that must contain a particular cookie pattern for the learning engine to learn that cookie.
Default value: AS_LEARNINGSETTINGS_DEFAULT_PERCENTTHRESHOLD
Maximum value: 100

<b>CSRFtagMinThreshold</b>
Minimum number of application firewall sessions that the learning engine must observe to learn cross-site request forgery (CSRF) tags.
Default value: AS_LEARNINGSETTINGS_DEFAULT_MINTHRESHOLD
Minimum value: 1

<b>CSRFtagPercentThreshold</b>
Minimum percentage of application firewall sessions that must contain a particular CSRF tag for the learning engine to learn that CSRF tag.
Default value: AS_LEARNINGSETTINGS_DEFAULT_PERCENTTHRESHOLD
Maximum value: 100

<b>fieldConsistencyMinThreshold</b>
Minimum number of application firewall sessions that the learning engine must observe to learn field consistency information.
Default value: AS_LEARNINGSETTINGS_DEFAULT_MINTHRESHOLD
Minimum value: 1

<b>fieldConsistencyPercentThreshold</b>
Minimum percentage of application firewall sessions that must contain a particular field consistency pattern for the learning engine to learn that field consistency pattern.
Default value: AS_LEARNINGSETTINGS_DEFAULT_PERCENTTHRESHOLD
Maximum value: 100

<b>crossSiteScriptingMinThreshold</b>
Minimum number of application firewall sessions that the learning engine must observe to learn HTML cross-site scripting patterns.
Default value: AS_LEARNINGSETTINGS_DEFAULT_MINTHRESHOLD
Minimum value: 1

<b>crossSiteScriptingPercentThreshold</b>
Minimum percentage of application firewall sessions that must contain a particular cross-site scripting pattern for the learning engine to learn that cross-site scripting pattern.
Default value: AS_LEARNINGSETTINGS_DEFAULT_PERCENTTHRESHOLD
Maximum value: 100

<b>SQLInjectionMinThreshold</b>
Minimum number of application firewall sessions that the learning engine must observe to learn HTML SQL injection patterns.
Default value: AS_LEARNINGSETTINGS_DEFAULT_MINTHRESHOLD
Minimum value: 1

<b>SQLInjectionPercentThreshold</b>
Minimum percentage of application firewall sessions that must contain a particular HTML SQL injection pattern for the learning engine to learn that HTML SQL injection pattern.
Default value: AS_LEARNINGSETTINGS_DEFAULT_PERCENTTHRESHOLD
Maximum value: 100

<b>fieldFormatMinThreshold</b>
Minimum number of application firewall sessions that the learning engine must observe to learn field formats.
Default value: AS_LEARNINGSETTINGS_DEFAULT_MINTHRESHOLD
Minimum value: 1

<b>fieldFormatPercentThreshold</b>
Minimum percentage of application firewall sessions that must contain a particular web form field pattern for the learning engine to recommend a field format for that form field.
Default value: AS_LEARNINGSETTINGS_DEFAULT_PERCENTTHRESHOLD
Maximum value: 100

<b>XMLWSIMinThreshold</b>
Minimum number of application firewall sessions that the learning engine must observe to learn web services interoperability (WSI) information.
Default value: AS_LEARNINGSETTINGS_DEFAULT_MINTHRESHOLD
Minimum value: 1

<b>XMLWSIPercentThreshold</b>
Minimum percentage of application firewall sessions that must contain a particular pattern for the learning engine to learn a web services interoperability (WSI) pattern.
Default value: AS_LEARNINGSETTINGS_DEFAULT_PERCENTTHRESHOLD
Maximum value: 100

<b>XMLAttachmentMinThreshold</b>
Minimum number of application firewall sessions that the learning engine must observe to learn XML attachment patterns.
Default value: AS_LEARNINGSETTINGS_DEFAULT_MINTHRESHOLD
Minimum value: 1

<b>XMLAttachmentPercentThreshold</b>
Minimum percentage of application firewall sessions that must contain a particular XML attachment pattern for the learning engine to learn that XML attachment pattern.
Default value: AS_LEARNINGSETTINGS_DEFAULT_PERCENTTHRESHOLD
Maximum value: 100



##unset appfw learningsettings

Use this command to remove appfw learningsettings settings.Refer to the set appfw learningsettings command for meanings of the arguments.


##Synopsys

unset appfw learningsettings &lt;profileName> [-startURLMinThreshold] [-startURLPercentThreshold] [-cookieConsistencyMinThreshold] [-cookieConsistencyPercentThreshold] [-CSRFtagMinThreshold] [-CSRFtagPercentThreshold] [-fieldConsistencyMinThreshold] [-fieldConsistencyPercentThreshold] [-crossSiteScriptingMinThreshold] [-crossSiteScriptingPercentThreshold] [-SQLInjectionMinThreshold] [-SQLInjectionPercentThreshold] [-fieldFormatMinThreshold] [-fieldFormatPercentThreshold] [-XMLWSIMinThreshold] [-XMLWSIPercentThreshold] [-XMLAttachmentMinThreshold] [-XMLAttachmentPercentThreshold]


##show appfw learningsettings

Displays the current application firewall learning settings for the specified profile.If no profile is specified, displays the current application firewall settings for all profiles on the NetScaler appliance.


##Synopsys

show appfw learningsettings [&lt;profileName>]


##Arguments

<b>profileName</b>
Name of the profile.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>startURLMinThreshold</b>
Minimum number of application firewall sessions that the learning engine must observe to learn start URLs.

<b>startURLPercentThreshold</b>
Minimum percentage of application firewall sessions that must contain a particular start URL pattern for the learning engine to learn that start URL.

<b>cookieConsistencyMinThreshold</b>
Minimum number of application firewall sessions that the learning engine must observe to learn cookies.

<b>cookieConsistencyPercentThreshold</b>
Minimum percentage of application firewall sessions that must contain a particular cookie pattern for the learning engine to learn that cookie.

<b>CSRFtagMinThreshold</b>
Minimum number of application firewall sessions that the learning engine must observe to learn cross-site request forgery (CSRF) tags.

<b>CSRFtagPercentThreshold</b>
Minimum percentage of application firewall sessions that must contain a particular CSRF tag for the learning engine to learn that CSRF tag.

<b>fieldConsistencyMinThreshold</b>
Minimum number of application firewall sessions that the learning engine must observe to learn field consistency information.

<b>fieldConsistencyPercentThreshold</b>
Minimum percentage of application firewall sessions that must contain a particular field consistency pattern for the learning engine to learn that field consistency pattern.

<b>crossSiteScriptingMinThreshold</b>
Minimum number of application firewall sessions that the learning engine must observe to learn HTML cross-site scripting patterns.

<b>crossSiteScriptingPercentThreshold</b>
Minimum percentage of application firewall sessions that must contain a particular cross-site scripting pattern for the learning engine to learn that cross-site scripting pattern.

<b>SQLInjectionMinThreshold</b>
Minimum number of application firewall sessions that the learning engine must observe to learn HTML SQL injection patterns.

<b>SQLInjectionPercentThreshold</b>
Minimum percentage of application firewall sessions that must contain a particular HTML SQL injection pattern for the learning engine to learn that HTML SQL injection pattern.

<b>fieldFormatMinThreshold</b>
Minimum number of application firewall sessions that the learning engine must observe to learn field formats.

<b>fieldFormatPercentThreshold</b>
Minimum percentage of application firewall sessions that must contain a particular web form field pattern for the learning engine to recommend a field format for that form field.

<b>XMLWSIMinThreshold</b>
Minimum threshold to learn XML Web Services Interoperability.

<b>XMLWSIPercentThreshold</b>
Minimum threshold (in percent) to learn XML Web Services Interoperability.

<b>XMLAttachmentMinThreshold</b>
Minimum threshold to learn XML Attachments.

<b>XMLAttachmentPercentThreshold</b>
Minimum threshold (in percent) to learn XML Attachments.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



