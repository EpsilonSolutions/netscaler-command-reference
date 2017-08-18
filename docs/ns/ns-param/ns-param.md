#ns param

The following operations can be performed on "ns param":


[set](#set-ns-param) | [unset](#unset-ns-param) | [show](#show-ns-param)

##set ns param

Sets the parameters of the NetScaler appliance.


##Synopsys

set ns param [-httpPort &lt;port> ...] [-maxConn &lt;positive_integer>] [-maxReq &lt;positive_integer>] [-cip ( ENABLED | DISABLED )  &lt;cipHeader>] [-cookieversion ( 0 | 1 )] [-secureCookie ( ENABLED | DISABLED )] [-pmtuMin &lt;positive_integer>] [-pmtuTimeout &lt;mins>] [-ftpPortRange &lt;int[-int]>] [-crPortRange &lt;int[-int]>] [-timezone &lt;timezone>] [-grantQuotaMaxClient &lt;positive_integer>] [-exclusiveQuotaMaxClient &lt;positive_integer>] [-grantQuotaSpillOver &lt;positive_integer>] [-exclusiveQuotaSpillOver &lt;positive_integer>] [-useproxyport ( ENABLED | DISABLED )] [-internaluserlogin ( ENABLED | DISABLED )] [-aftpAllowRandomSourcePort ( ENABLED | DISABLED )] [-icaPorts &lt;port> ...] [-tcpCIP ( ENABLED | DISABLED )] [-servicePathIngressVLAN &lt;positive_integer>] [-secureicaPorts &lt;port> ...]


##Arguments

<b>httpPort</b>
HTTP ports on the web server. This allows the system to perform connection off-load for any client request that has a destination port matching one of these configured ports.
Minimum value: 1
Maximum value: 65535

<b>maxConn</b>
Maximum number of connections that will be made from the appliance to the web server(s) attached to it. The value entered here is applied globally to all attached servers.
Default value: 0
Minimum value: 0
Maximum value: 4294967294

<b>maxReq</b>
Maximum number of requests that the system can pass on a particular connection between the appliance and a server attached to it. Setting this value to 0 allows an unlimited number of requests to be passed. This value is overridden by the maximum number of requests configured on the individual service.
Minimum value: 0
Maximum value: 65535

<b>cip</b>
Enable or disable the insertion of the actual client IP address into the HTTP header request passed from the client to one, some, or all servers attached to the system. The passed address can then be accessed through a minor modification to the server.
* If the CIP header is specified, it will be used as the client IP header.
* If the CIP header is not specified, the value that has been set will be used as the client IP header.
Possible values: ENABLED, DISABLED

<b>cipHeader</b>
Text that will be used as the client IP address header.

<b>cookieversion</b>
Version of the cookie inserted by the system.
Possible values: 0, 1

<b>secureCookie</b>
Enable or disable secure flag for persistence cookie.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>pmtuMin</b>
Minimum path MTU value that NetScaler will process in the ICMP fragmentation needed message. If the ICMP message contains a value less than this value, then this value is used instead.
Default value: 576
Minimum value: 168
Maximum value: 1500

<b>pmtuTimeout</b>
Interval, in minutes, for flushing the PMTU entries.
Default value: 10
Minimum value: 1
Maximum value: 1440

<b>ftpPortRange</b>
Minimum and maximum port (port range) that FTP services are allowed to use.
Minimum value: 1024
Maximum value: 64000

<b>crPortRange</b>
Port range for cache redirection services.
Minimum value: 1
Maximum value: 65535

<b>timezone</b>
Time zone for the NetScaler appliance. Name of the time zone should be specified as argument.
Possible values: CoordinatedUniversalTime, GMT+01:00-CET-Europe/Andorra, GMT+04:00-GST-Asia/Dubai, GMT+04:30-AFT-Asia/Kabul, GMT-04:00-AST-America/Antigua, GMT-04:00-AST-America/Anguilla, GMT+01:00-CET-Europe/Tirane, GMT+04:00-+04-Asia/Yerevan, GMT+01:00-WAT-Africa/Luanda, GMT+13:00-NZDT-Antarctica/McMurdo, GMT+08:00-+08-Antarctica/Casey, GMT+07:00-+07-Antarctica/Davis, GMT+10:00-+10-Antarctica/DumontDUrville, GMT+05:00-+05-Antarctica/Mawson, GMT-03:00-CLST-Antarctica/Palmer, GMT-03:00--03-Antarctica/Rothera, GMT+03:00-+03-Antarctica/Syowa, GMT+00:00-+00-Antarctica/Troll, GMT+06:00-+06-Antarctica/Vostok, GMT-03:00-ART-America/Argentina/Buenos_Aires, GMT-03:00-ART-America/Argentina/Cordoba, GMT-03:00-ART-America/Argentina/Salta, GMT-03:00-ART-America/Argentina/Jujuy, GMT-03:00-ART-America/Argentina/Tucuman, GMT-03:00-ART-America/Argentina/Catamarca, GMT-03:00-ART-America/Argentina/La_Rioja, GMT-03:00-ART-America/Argentina/San_Juan, GMT-03:00-ART-America/Argentina/Mendoza, GMT-03:00-ART-America/Argentina/San_Luis, GMT-03:00-ART-America/Argentina/Rio_Gallegos, GMT-03:00-ART-America/Argentina/Ushuaia, GMT-11:00-SST-Pacific/Pago_Pago, GMT+01:00-CET-Europe/Vienna, GMT+11:00-LHDT-Australia/Lord_Howe, GMT+11:00-MIST-Antarctica/Macquarie, GMT+11:00-AEDT-Australia/Hobart, GMT+11:00-AEDT-Australia/Currie, GMT+11:00-AEDT-Australia/Melbourne, GMT+11:00-AEDT-Australia/Sydney, GMT+10:30-ACDT-Australia/Broken_Hill, GMT+10:00-AEST-Australia/Brisbane, GMT+10:00-AEST-Australia/Lindeman, GMT+10:30-ACDT-Australia/Adelaide, GMT+09:30-ACST-Australia/Darwin, GMT+08:00-AWST-Australia/Perth, GMT+08:45-ACWST-Australia/Eucla, GMT-04:00-AST-America/Aruba, GMT+02:00-EET-Europe/Mariehamn, GMT+04:00-+04-Asia/Baku, GMT+01:00-CET-Europe/Sarajevo, GMT-04:00-AST-America/Barbados, GMT+06:00-BDT-Asia/Dhaka, GMT+01:00-CET-Europe/Brussels, GMT+00:00-GMT-Africa/Ouagadougou, GMT+02:00-EET-Europe/Sofia, GMT+03:00-AST-Asia/Bahrain, GMT+02:00-CAT-Africa/Bujumbura, GMT+01:00-WAT-Africa/Porto-Novo, GMT-04:00-AST-America/St_Barthelemy, GMT-04:00-AST-Atlantic/Bermuda, GMT+08:00-BNT-Asia/Brunei, GMT-04:00-BOT-America/La_Paz, GMT-04:00-AST-America/Kralendijk, GMT-02:00-FNT-America/Noronha, GMT-03:00-BRT-America/Belem, GMT-03:00-BRT-America/Fortaleza, GMT-03:00-BRT-America/Recife, GMT-03:00-BRT-America/Araguaina, GMT-03:00-BRT-America/Maceio, GMT-03:00-BRT-America/Bahia, GMT-03:00-BRT-America/Sao_Paulo, GMT-04:00-AMT-America/Campo_Grande, GMT-04:00-AMT-America/Cuiaba, GMT-03:00-BRT-America/Santarem, GMT-04:00-AMT-America/Porto_Velho, GMT-04:00-AMT-America/Boa_Vista, GMT-04:00-AMT-America/Manaus, GMT-05:00-ACT-America/Eirunepe, GMT-05:00-ACT-America/Rio_Branco, GMT-05:00-EST-America/Nassau, GMT+06:00-BTT-Asia/Thimphu, GMT+02:00-CAT-Africa/Gaborone, GMT+03:00-+03-Europe/Minsk, GMT-06:00-CST-America/Belize, GMT-03:30-NST-America/St_Johns, GMT-04:00-AST-America/Halifax, GMT-04:00-AST-America/Glace_Bay, GMT-04:00-AST-America/Moncton, GMT-04:00-AST-America/Goose_Bay, GMT-04:00-AST-America/Blanc-Sablon, GMT-05:00-EST-America/Toronto, GMT-05:00-EST-America/Nipigon, GMT-05:00-EST-America/Thunder_Bay, GMT-05:00-EST-America/Iqaluit, GMT-05:00-EST-America/Pangnirtung, GMT-05:00-EST-America/Atikokan, GMT-06:00-CST-America/Winnipeg, GMT-06:00-CST-America/Rainy_River, GMT-06:00-CST-America/Resolute, GMT-06:00-CST-America/Rankin_Inlet, GMT-06:00-CST-America/Regina, GMT-06:00-CST-America/Swift_Current, GMT-07:00-MST-America/Edmonton, GMT-07:00-MST-America/Cambridge_Bay, GMT-07:00-MST-America/Yellowknife, GMT-07:00-MST-America/Inuvik, GMT-07:00-MST-America/Creston, GMT-07:00-MST-America/Dawson_Creek, GMT-07:00-MST-America/Fort_Nelson, GMT-08:00-PST-America/Vancouver, GMT-08:00-PST-America/Whitehorse, GMT-08:00-PST-America/Dawson, GMT+06:30-CCT-Indian/Cocos, GMT+01:00-WAT-Africa/Kinshasa, GMT+02:00-CAT-Africa/Lubumbashi, GMT+01:00-WAT-Africa/Bangui, GMT+01:00-WAT-Africa/Brazzaville, GMT+01:00-CET-Europe/Zurich, GMT+00:00-GMT-Africa/Abidjan, GMT-10:00-CKT-Pacific/Rarotonga, GMT-03:00-CLST-America/Santiago, GMT-05:00-EASST-Pacific/Easter, GMT+01:00-WAT-Africa/Douala, GMT+08:00-CST-Asia/Shanghai, GMT+06:00-XJT-Asia/Urumqi, GMT-05:00-COT-America/Bogota, GMT-06:00-CST-America/Costa_Rica, GMT-05:00-CST-America/Havana, GMT-01:00-CVT-Atlantic/Cape_Verde, GMT-04:00-AST-America/Curacao, GMT+07:00-CXT-Indian/Christmas, GMT+02:00-EET-Asia/Nicosia, GMT+01:00-CET-Europe/Prague, GMT+01:00-CET-Europe/Berlin, GMT+01:00-CET-Europe/Busingen, GMT+03:00-EAT-Africa/Djibouti, GMT+01:00-CET-Europe/Copenhagen, GMT-04:00-AST-America/Dominica, GMT-04:00-AST-America/Santo_Domingo, GMT+01:00-CET-Africa/Algiers, GMT-05:00-ECT-America/Guayaquil, GMT-06:00-GALT-Pacific/Galapagos, GMT+02:00-EET-Europe/Tallinn, GMT+02:00-EET-Africa/Cairo, GMT+00:00-WET-Africa/El_Aaiun, GMT+03:00-EAT-Africa/Asmara, GMT+01:00-CET-Europe/Madrid, GMT+01:00-CET-Africa/Ceuta, GMT+00:00-WET-Atlantic/Canary, GMT+03:00-EAT-Africa/Addis_Ababa, GMT+02:00-EET-Europe/Helsinki, GMT+12:00-FJT-Pacific/Fiji, GMT-03:00-FKST-Atlantic/Stanley, GMT+10:00-CHUT-Pacific/Chuuk, GMT+11:00-PONT-Pacific/Pohnpei, GMT+11:00-KOST-Pacific/Kosrae, GMT+00:00-WET-Atlantic/Faroe, GMT+01:00-CET-Europe/Paris, GMT+01:00-WAT-Africa/Libreville, GMT+00:00-GMT-Europe/London, GMT-04:00-AST-America/Grenada, GMT+04:00-+04-Asia/Tbilisi, GMT-03:00-GFT-America/Cayenne, GMT+00:00-GMT-Europe/Guernsey, GMT+00:00-GMT-Africa/Accra, GMT+01:00-CET-Europe/Gibraltar, GMT-03:00-WGT-America/Godthab, GMT+00:00-GMT-America/Danmarkshavn, GMT-01:00-EGT-America/Scoresbysund, GMT-04:00-AST-America/Thule, GMT+00:00-GMT-Africa/Banjul, GMT+00:00-GMT-Africa/Conakry, GMT-04:00-AST-America/Guadeloupe, GMT+01:00-WAT-Africa/Malabo, GMT+02:00-EET-Europe/Athens, GMT-02:00-GST-Atlantic/South_Georgia, GMT-06:00-CST-America/Guatemala, GMT+10:00-ChST-Pacific/Guam, GMT+00:00-GMT-Africa/Bissau, GMT-04:00-GYT-America/Guyana, GMT+08:00-HKT-Asia/Hong_Kong, GMT-06:00-CST-America/Tegucigalpa, GMT+01:00-CET-Europe/Zagreb, GMT-05:00-EST-America/Port-au-Prince, GMT+01:00-CET-Europe/Budapest, GMT+07:00-WIB-Asia/Jakarta, GMT+07:00-WIB-Asia/Pontianak, GMT+08:00-WITA-Asia/Makassar, GMT+09:00-WIT-Asia/Jayapura, GMT+00:00-GMT-Europe/Dublin, GMT+02:00-IST-Asia/Jerusalem, GMT+00:00-GMT-Europe/Isle_of_Man, GMT+05:30-IST-Asia/Kolkata, GMT+06:00-IOT-Indian/Chagos, GMT+03:00-AST-Asia/Baghdad, GMT+03:30-IRST-Asia/Tehran, GMT+00:00-GMT-Atlantic/Reykjavik, GMT+01:00-CET-Europe/Rome, GMT+00:00-GMT-Europe/Jersey, GMT-05:00-EST-America/Jamaica, GMT+02:00-EET-Asia/Amman, GMT+09:00-JST-Asia/Tokyo, GMT+03:00-EAT-Africa/Nairobi, GMT+06:00-+06-Asia/Bishkek, GMT+07:00-ICT-Asia/Phnom_Penh, GMT+12:00-GILT-Pacific/Tarawa, GMT+13:00-PHOT-Pacific/Enderbury, GMT+14:00-LINT-Pacific/Kiritimati, GMT+03:00-EAT-Indian/Comoro, GMT-04:00-AST-America/St_Kitts, GMT+08:30-KST-Asia/Pyongyang, GMT+09:00-KST-Asia/Seoul, GMT+03:00-AST-Asia/Kuwait, GMT-05:00-EST-America/Cayman, GMT+06:00-+06-Asia/Almaty, GMT+06:00-+06-Asia/Qyzylorda, GMT+05:00-+05-Asia/Aqtobe, GMT+05:00-+05-Asia/Aqtau, GMT+05:00-+05-Asia/Oral, GMT+07:00-ICT-Asia/Vientiane, GMT+02:00-EET-Asia/Beirut, GMT-04:00-AST-America/St_Lucia, GMT+01:00-CET-Europe/Vaduz, GMT+05:30-IST-Asia/Colombo, GMT+00:00-GMT-Africa/Monrovia, GMT+02:00-SAST-Africa/Maseru, GMT+02:00-EET-Europe/Vilnius, GMT+01:00-CET-Europe/Luxembourg, GMT+02:00-EET-Europe/Riga, GMT+02:00-EET-Africa/Tripoli, GMT+00:00-WET-Africa/Casablanca, GMT+01:00-CET-Europe/Monaco, GMT+02:00-EET-Europe/Chisinau, GMT+01:00-CET-Europe/Podgorica, GMT-04:00-AST-America/Marigot, GMT+03:00-EAT-Indian/Antananarivo, GMT+12:00-MHT-Pacific/Majuro, GMT+12:00-MHT-Pacific/Kwajalein, GMT+01:00-CET-Europe/Skopje, GMT+00:00-GMT-Africa/Bamako, GMT+06:30-MMT-Asia/Yangon, GMT+08:00-ULAT-Asia/Ulaanbaatar, GMT+07:00-HOVT-Asia/Hovd, GMT+08:00-CHOT-Asia/Choibalsan, GMT+08:00-CST-Asia/Macau, GMT+10:00-ChST-Pacific/Saipan, GMT-04:00-AST-America/Martinique, GMT+00:00-GMT-Africa/Nouakchott, GMT-04:00-AST-America/Montserrat, GMT+01:00-CET-Europe/Malta, GMT+04:00-MUT-Indian/Mauritius, GMT+05:00-MVT-Indian/Maldives, GMT+02:00-CAT-Africa/Blantyre, GMT-06:00-CST-America/Mexico_City, GMT-05:00-EST-America/Cancun, GMT-06:00-CST-America/Merida, GMT-06:00-CST-America/Monterrey, GMT-06:00-CST-America/Matamoros, GMT-07:00-MST-America/Mazatlan, GMT-07:00-MST-America/Chihuahua, GMT-07:00-MST-America/Ojinaga, GMT-07:00-MST-America/Hermosillo, GMT-08:00-PST-America/Tijuana, GMT-06:00-CST-America/Bahia_Banderas, GMT+08:00-MYT-Asia/Kuala_Lumpur, GMT+08:00-MYT-Asia/Kuching, GMT+02:00-CAT-Africa/Maputo, GMT+02:00-WAST-Africa/Windhoek, GMT+11:00-NCT-Pacific/Noumea, GMT+01:00-WAT-Africa/Niamey, GMT+11:00-NFT-Pacific/Norfolk, GMT+01:00-WAT-Africa/Lagos, GMT-06:00-CST-America/Managua, GMT+01:00-CET-Europe/Amsterdam, GMT+01:00-CET-Europe/Oslo, GMT+05:45-NPT-Asia/Kathmandu, GMT+12:00-NRT-Pacific/Nauru, GMT-11:00-NUT-Pacific/Niue, GMT+13:00-NZDT-Pacific/Auckland, GMT+13:45-CHADT-Pacific/Chatham, GMT+04:00-GST-Asia/Muscat, GMT-05:00-EST-America/Panama, GMT-05:00-PET-America/Lima, GMT-10:00-TAHT-Pacific/Tahiti, GMT-09:30-MART-Pacific/Marquesas, GMT-09:00-GAMT-Pacific/Gambier, GMT+10:00-PGT-Pacific/Port_Moresby, GMT+11:00-BST-Pacific/Bougainville, GMT+08:00-PHT-Asia/Manila, GMT+05:00-PKT-Asia/Karachi, GMT+01:00-CET-Europe/Warsaw, GMT-03:00-PMST-America/Miquelon, GMT-08:00-PST-Pacific/Pitcairn, GMT-04:00-AST-America/Puerto_Rico, GMT+02:00-EET-Asia/Gaza, GMT+02:00-EET-Asia/Hebron, GMT+00:00-WET-Europe/Lisbon, GMT+00:00-WET-Atlantic/Madeira, GMT-01:00-AZOT-Atlantic/Azores, GMT+09:00-PWT-Pacific/Palau, GMT-03:00-PYST-America/Asuncion, GMT+03:00-AST-Asia/Qatar, GMT+04:00-RET-Indian/Reunion, GMT+02:00-EET-Europe/Bucharest, GMT+01:00-CET-Europe/Belgrade, GMT+02:00-EET-Europe/Kaliningrad, GMT+03:00-MSK-Europe/Moscow, GMT+03:00-MSK-Europe/Simferopol, GMT+03:00-+03-Europe/Volgograd, GMT+03:00-+03-Europe/Kirov, GMT+04:00-+04-Europe/Astrakhan, GMT+04:00-+04-Europe/Samara, GMT+04:00-+04-Europe/Ulyanovsk, GMT+05:00-+05-Asia/Yekaterinburg, GMT+06:00-+06-Asia/Omsk, GMT+07:00-+07-Asia/Novosibirsk, GMT+07:00-+07-Asia/Barnaul, GMT+07:00-+07-Asia/Tomsk, GMT+07:00-+07-Asia/Novokuznetsk, GMT+07:00-+07-Asia/Krasnoyarsk, GMT+08:00-+08-Asia/Irkutsk, GMT+09:00-+09-Asia/Chita, GMT+09:00-+09-Asia/Yakutsk, GMT+09:00-+09-Asia/Khandyga, GMT+10:00-+10-Asia/Vladivostok, GMT+10:00-+10-Asia/Ust-Nera, GMT+11:00-+11-Asia/Magadan, GMT+11:00-+11-Asia/Sakhalin, GMT+11:00-+11-Asia/Srednekolymsk, GMT+12:00-+12-Asia/Kamchatka, GMT+12:00-+12-Asia/Anadyr, GMT+02:00-CAT-Africa/Kigali, GMT+03:00-AST-Asia/Riyadh, GMT+11:00-SBT-Pacific/Guadalcanal, GMT+04:00-SCT-Indian/Mahe, GMT+03:00-EAT-Africa/Khartoum, GMT+01:00-CET-Europe/Stockholm, GMT+08:00-SGT-Asia/Singapore, GMT+00:00-GMT-Atlantic/St_Helena, GMT+01:00-CET-Europe/Ljubljana, GMT+01:00-CET-Arctic/Longyearbyen, GMT+01:00-CET-Europe/Bratislava, GMT+00:00-GMT-Africa/Freetown, GMT+01:00-CET-Europe/San_Marino, GMT+00:00-GMT-Africa/Dakar, GMT+03:00-EAT-Africa/Mogadishu, GMT-03:00-SRT-America/Paramaribo, GMT+03:00-EAT-Africa/Juba, GMT+00:00-GMT-Africa/Sao_Tome, GMT-06:00-CST-America/El_Salvador, GMT-04:00-AST-America/Lower_Princes, GMT+02:00-EET-Asia/Damascus, GMT+02:00-SAST-Africa/Mbabane, GMT-04:00-AST-America/Grand_Turk, GMT+01:00-WAT-Africa/Ndjamena, GMT+05:00-+05-Indian/Kerguelen, GMT+00:00-GMT-Africa/Lome, GMT+07:00-ICT-Asia/Bangkok, GMT+05:00-+05-Asia/Dushanbe, GMT+13:00-TKT-Pacific/Fakaofo, GMT+09:00-TLT-Asia/Dili, GMT+05:00-+05-Asia/Ashgabat, GMT+01:00-CET-Africa/Tunis, GMT+13:00-TOT-Pacific/Tongatapu, GMT+03:00-+03-Europe/Istanbul, GMT-04:00-AST-America/Port_of_Spain, GMT+12:00-TVT-Pacific/Funafuti, GMT+08:00-CST-Asia/Taipei, GMT+03:00-EAT-Africa/Dar_es_Salaam, GMT+02:00-EET-Europe/Kiev, GMT+02:00-EET-Europe/Uzhgorod, GMT+02:00-EET-Europe/Zaporozhye, GMT+03:00-EAT-Africa/Kampala, GMT-10:00-HST-Pacific/Johnston, GMT-11:00-SST-Pacific/Midway, GMT+12:00-WAKT-Pacific/Wake, GMT-05:00-EST-America/New_York, GMT-05:00-EST-America/Detroit, GMT-05:00-EST-America/Kentucky/Louisville, GMT-05:00-EST-America/Kentucky/Monticello, GMT-05:00-EST-America/Indiana/Indianapolis, GMT-05:00-EST-America/Indiana/Vincennes, GMT-05:00-EST-America/Indiana/Winamac, GMT-05:00-EST-America/Indiana/Marengo, GMT-05:00-EST-America/Indiana/Petersburg, GMT-05:00-EST-America/Indiana/Vevay, GMT-06:00-CST-America/Chicago, GMT-06:00-CST-America/Indiana/Tell_City, GMT-06:00-CST-America/Indiana/Knox, GMT-06:00-CST-America/Menominee, GMT-06:00-CST-America/North_Dakota/Center, GMT-06:00-CST-America/North_Dakota/New_Salem, GMT-06:00-CST-America/North_Dakota/Beulah, GMT-07:00-MST-America/Denver, GMT-07:00-MST-America/Boise, GMT-07:00-MST-America/Phoenix, GMT-08:00-PST-America/Los_Angeles, GMT-09:00-AKST-America/Anchorage, GMT-09:00-AKST-America/Juneau, GMT-09:00-AKST-America/Sitka, GMT-09:00-AKST-America/Metlakatla, GMT-09:00-AKST-America/Yakutat, GMT-09:00-AKST-America/Nome, GMT-10:00-HST-America/Adak, GMT-10:00-HST-Pacific/Honolulu, GMT-03:00-UYT-America/Montevideo, GMT+05:00-+05-Asia/Samarkand, GMT+05:00-+05-Asia/Tashkent, GMT+01:00-CET-Europe/Vatican, GMT-04:00-AST-America/St_Vincent, GMT-04:00-VET-America/Caracas, GMT-04:00-AST-America/Tortola, GMT-04:00-AST-America/St_Thomas, GMT+07:00-ICT-Asia/Ho_Chi_Minh, GMT+11:00-VUT-Pacific/Efate, GMT+12:00-WFT-Pacific/Wallis, GMT+14:00-WSDT-Pacific/Apia, GMT+03:00-AST-Asia/Aden, GMT+03:00-EAT-Indian/Mayotte, GMT+02:00-SAST-Africa/Johannesburg, GMT+02:00-CAT-Africa/Lusaka, GMT+02:00-CAT-Africa/Harare

<b>grantQuotaMaxClient</b>
Percentage of shared quota to be granted at a time for maxClient.
Default value: 10
Minimum value: 0
Maximum value: 100

<b>exclusiveQuotaMaxClient</b>
Percentage of maxClient to be given to PEs.
Default value: 80
Minimum value: 0
Maximum value: 100

<b>grantQuotaSpillOver</b>
Percentage of shared quota to be granted at a time for spillover.
Default value: 10
Minimum value: 0
Maximum value: 100

<b>exclusiveQuotaSpillOver</b>
Percentage of maximum limit to be given to PEs.
Default value: 80
Minimum value: 0
Maximum value: 100

<b>useproxyport</b>
Enable/Disable use_proxy_port setting
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>internaluserlogin</b>
Enables/disables the internal user from logging in to the appliance. Before disabling internal user login, you must have key-based authentication set up on the appliance. The file name for the key pair must be "ns_comm_key".
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>aftpAllowRandomSourcePort</b>
Allow the FTP server to come from a random source port for active FTP data connections
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>icaPorts</b>
The ICA ports on the Web server. This allows the system to perform connection off-load for any
                      client request that has a destination port matching one of these configured ports.
Minimum value: 1

<b>tcpCIP</b>
Enable or disable the insertion of the client TCP/IP header in TCP payload passed from the client to one, some, or all servers attached to the system. The passed address can then be accessed through a minor modification to the server.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>servicePathIngressVLAN</b>
VLAN on which the subscriber traffic arrives on the appliance.
Minimum value: 1

<b>secureicaPorts</b>
The Secure ICA ports on the Web server. This allows the system to perform connection off-load for any
            client request that has a destination port matching one of these configured ports.
Minimum value: 1



##unset ns param

Removes the attributes of the NetScaler parameters. Attributes for which a default value is available revert to their default values. Refer to the 'set ns param' command for a description of the parameters..Refer to the set ns param command for meanings of the arguments.


##Synopsys

unset ns param [-ftpPortRange] [-crPortRange] [-timezone] [-aftpAllowRandomSourcePort] [-httpPort] [-maxConn] [-maxReq] [-cip] [-cipHeader] [-cookieversion] [-secureCookie] [-pmtuMin] [-pmtuTimeout] [-grantQuotaMaxClient] [-exclusiveQuotaMaxClient] [-grantQuotaSpillOver] [-exclusiveQuotaSpillOver] [-useproxyport] [-internaluserlogin] [-icaPorts] [-tcpCIP] [-servicePathIngressVLAN] [-secureicaPorts]


##show ns param

Displays the information of the parameters of the NetScaler appliance that were set by using the 'set ns param' command.


##Synopsys

show ns param


##Outputs

<b>httpPort</b>
The HTTP ports on the Web server.

<b>maxConn</b>
Maximum Number of Connections.

<b>maxReq</b>
Maxmimum Number of requests that can be handled.

<b>cip</b>
Insertion of client IP address into the HTTP header.

<b>cipHeader</b>
The text that will be used as the client IP header.

<b>cookieversion</b>
Version of the cookie inserted by the system.

<b>secureCookie</b>
Enable or disable secure flag for persistence cookie.

<b>pmtuMin</b>
Minimum path MTU value that NetScaler will process in the ICMP fragmentation needed message. If the ICMP message contains a value less than this value, then this value is used instead.

<b>pmtuTimeout</b>
Interval, in minutes, for flushing the PMTU entries.

<b>ftpPortRange</b>
Minimum and maximum port (port range) that FTP services are allowed to use.

<b>crPortRange</b>
Port range for cache redirection services.

<b>timezone</b>
Time zone for the NetScaler appliance. Name of the time zone should be specified as argument.

<b>grantQuotaMaxClient</b>
Percentage of shared quota to be granted at a time for maxClient.

<b>exclusiveQuotaMaxClient</b>
Percentage of maxClient to be given to PEs.

<b>grantQuotaSpillOver</b>
Percentage of shared quota to be granted at a time for spillover.

<b>exclusiveQuotaSpillOver</b>
Percentage of maximum limit to be given to PEs.

<b>useproxyport</b>
Enable/Disable use_proxy_port setting

<b>internaluserlogin</b>
Enables/disables the internal user from logging in to the appliance. Before disabling internal user login, you must have key-based authentication set up on the appliance. The file name for the key pair must be "ns_comm_key".

<b>aftpAllowRandomSourcePort</b>
Allow the FTP server to come from a random source port for active FTP data connections

<b>icaPorts</b>
The ICA ports on the Web server. This allows the system to perform connection off-load for any
                      client request that has a destination port matching one of these configured ports.

<b>tcpCIP</b>
Enable or disable the insertion of the client TCP/IP header in TCP payload passed from the client to one, some, or all servers attached to the system. The passed address can then be accessed through a minor modification to the server.

<b>servicePathIngressVLAN</b>
VLAN on which the subscriber traffic arrives on the appliance.

<b>secureicaPorts</b>
The Secure ICA ports on the Web server. This allows the system to perform connection off-load for any
            client request that has a destination port matching one of these configured ports.



