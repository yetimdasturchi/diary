---
toc: false
title: "Datalife engine postlarini mamlakatlar bo'yicha boshqarish"
description: "Ko'p holatlarda veb sayt doirasidagi postlarni ma'lum mamlakatlar doirasida boshqarishga to'g'ri keladi. Bugungi kunda asosiy veb saytlar dle cms..."
keywords: "datalife, engine, sayt, post, postlar, mamlakat, lifehack"
---

Ko'p holatlarda veb sayt doirasidagi postlarni ma'lum mamlakatlar doirasida boshqarishga to'g'ri keladi. Bugungi kunda asosiy veb saytlar datalife engine cms orqali ishlagani sababli ushbu muammoni hal etish uchun cms kodlariga oz-moz o'rgatirish kiritish orqali hal qilish mumkin.

DLE strukturasiga nazar soladigan bo'lsak postlar uchun tizim doirasida `xfields` ya'ni qo'shimcha maydonlar kiritish imkoniyati mavjud. Biz ham shu imkoniyat doirasiga kichik o'rgartirish kiritamiz.

Ishni qo'shimcha maydon kiritishdan boshlasak.

1. Boshqruv panelining ***Добавление нового дополнительного поля*** bo'limidan `country` nomi bilan yangi maydon kiritamiz va ***Значение по умолчанию*** qismiga quyidagilarni kiritamiz. Maydonni saqlab tizim kodlarini tahrirlashga o'tamiz.

![xfields]({contents_url="blog/datalife-engine-postlarini-mamlakatlar-boyicha-boshqarish/xfileds-panel.jpeg"})

```
AFG|Afghanistan
ALA|Aland Islands
ALB|Albania
DZA|Algeria
ASM|American Samoa
_AND|Andorra
AGO|Angola
AIA|Anguilla
ATA|Antarctica
ATG|Antigua and Barbuda
ARG|Argentina
ARM|Armenia
ABW|Aruba
AUS|Australia
AUT|Austria
AZE|Azerbaijan
BHS|Bahamas
BHR|Bahrain
BGD|Bangladesh
BRB|Barbados
BLR|Belarus
BEL|Belgium
BLZ|Belize
BEN|Benin
BMU|Bermuda
BTN|Bhutan
BOL|Bolivia (Plurinational State of)
BES|Bonaire
BIH|Bosnia and Herzegovina
BWA|Botswana
BVT|Bouvet Island
BRA|Brazil
IOT|British Indian Ocean Territory
BRN|Brunei Darussalam
BGR|Bulgaria
BFA|Burkina Faso
BDI|Burundi
KHM|Cambodia
CMR|Cameroon
CAN|Canada
CPV|Cabo Verde
CYM|Cayman Islands
CAF|Central African Republic
TCD|Chad
CHL|Chile
CHN|China
CXR|Christmas Island
CCK|Cocos (Keeling) Islands
COL|Colombia
COM|Comoros
COG|Congo
COD|Congo (Democratic Republic of the)
COK|Cook Islands
CRI|Costa Rica
CIV|Cote d`Ivoire
HRV|Croatia
CUB|Cuba
CUW|Curacao
CYP|Cyprus
CZE|Czech Republic
DNK|Denmark
DJI|Djibouti
DMA|Dominica
DOM|Dominican Republic
ECU|Ecuador
EGY|Egypt
SLV|El Salvador
GNQ|Equatorial Guinea
ERI|Eritrea
EST|Estonia
ETH|Ethiopia
FLK|Falkland Islands (Malvinas)
FRO|Faroe Islands
FJI|Fiji
FIN|Finland
FRA|France
GUF|French Guiana
PYF|French Polynesia
ATF|French Southern Territories
GAB|Gabon
GMB|Gambia
GEO|Georgia
DEU|Germany
GHA|Ghana
GIB|Gibraltar
GRC|Greece
GRL|Greenland
GRD|Grenada
GLP|Guadeloupe
GUM|Guam
GTM|Guatemala
GGY|Guernsey
GIN|Guinea
GNB|Guinea-Bissau
GUY|Guyana
HTI|Haiti
HMD|Heard Island and McDonald Islands
VAT|Holy See
HND|Honduras
HKG|Hong Kong
HUN|Hungary
ISL|Iceland
IND|India
IDN|Indonesia
IRN|Iran (Islamic Republic of)
IRQ|Iraq
IRL|Ireland
IMN|Isle of Man
ISR|Israel
ITA|Italy
JAM|Jamaica
JPN|Japan
JEY|Jersey
JOR|Jordan
KAZ|Kazakhstan
KEN|Kenya
KIR|Kiribati
PRK|Korea (Democratic People`s Republic of)
KOR|Korea (Republic of)
KWT|Kuwait
KGZ|Kyrgyzstan
LAO|Lao People`s Democratic Republic
LVA|Latvia
LBN|Lebanon
LSO|Lesotho
LBR|Liberia
LBY|Libya
LIE|Liechtenstein
LTU|Lithuania
LUX|Luxembourg
MAC|Macao
MKD|Macedonia
MDG|Madagascar
MWI|Malawi
MYS|Malaysia
MDV|Maldives
MLI|Mali
MLT|Malta
MHL|Marshall Islands
MTQ|Martinique
MRT|Mauritania
MUS|Mauritius
MYT|Mayotte
MEX|Mexico
FSM|Micronesia (Federated States of)
MDA|Moldova (Republic of)
MCO|Monaco
MNG|Mongolia
MNE|Montenegro
MSR|Montserrat
MAR|Morocco
MOZ|Mozambique
MMR|Myanmar
NAM|Namibia
NRU|Nauru
NPL|Nepal
NLD|Netherlands
NCL|New Caledonia
NZL|New Zealand
NIC|Nicaragua
NER|Niger
NGA|Nigeria
NIU|Niue
NFK|Norfolk Island
MNP|Northern Mariana Islands
NOR|Norway
OMN|Oman
PAK|Pakistan
PLW|Palau
PSE|Palestine
PAN|Panama
PNG|Papua New Guinea
PRY|Paraguay
PER|Peru
PHL|Philippines
PCN|Pitcairn
POL|Poland
PRT|Portugal
PRI|Puerto Rico
QAT|Qatar
REU|Reunion
ROU|Romania
RUS|Russian Federation
RWA|Rwanda
BLM|Saint Barthelemy
SHN|Saint Helena
KNA|Saint Kitts and Nevis
LCA|Saint Lucia
MAF|Saint Martin (French part)
SPM|Saint Pierre and Miquelon
VCT|Saint Vincent and the Grenadines
WSM|Samoa
SMR|San Marino
STP|Sao Tome and Principe
SAU|Saudi Arabia
SEN|Senegal
SRB|Serbia
SYC|Seychelles
SLE|Sierra Leone
SGP|Singapore
SXM|Sint Maarten (Dutch part)
SVK|Slovakia
SVN|Slovenia
SLB|Solomon Islands
SOM|Somalia
ZAF|South Africa
SGS|South Georgia and the South Sandwich Islands
SSD|South Sudan
ESP|Spain
LKA|Sri Lanka
SDN|Sudan
SUR|Suriname
SJM|Svalbard and Jan Mayen
SWZ|Swaziland
SWE|Sweden
CHE|Switzerland
SYR|Syrian Arab Republic
TWN|Taiwan (Province of China)
TJK|Tajikistan
TZA|Tanzania
THA|Thailand
TLS|Timor-Leste
TGO|Togo
TKL|Tokelau
TON|Tonga
TTO|Trinidad and Tobago
TUN|Tunisia
TUR|Turkey
TKM|Turkmenistan
TCA|Turks and Caicos Islands
TUV|Tuvalu
UGA|Uganda
UKR|Ukraine
ARE|United Arab Emirates
GBR|United Kingdom of Great Britain and Northern Ireland
USA|United States of America
UMI|United States Minor Outlying Islands
URY|Uruguay
UZB|Uzbekistan
VUT|Vanuatu
VEN|Venezuela (Bolivarian Republic of)
VNM|Viet Nam
VGB|Virgin Islands (British)
VIR|Virgin Islands (U.S.)
WLF|Wallis and Futuna
ESH|Western Sahara
YEM|Yemen
ZMB|Zambia
ZWE|Zimbabwe
```

 2. `engine/inc/` papkasida joylashgan `xfields.php` faylidan `} elseif ($value[3] == "select") {` qatorini topib blokni quyidagi holatdan:
 
 ```php
 } elseif ($value[3] == "select") {

if ($xfieldmode == "site") {

$select = "<select name=\"xfield[$fieldname]\">";

} else {

$select = "<select class=\"uniform\" name=\"xfield[$fieldname]\">";

}

if ( !isset($fieldvalue) ) $fieldvalue = "";

$fieldvalue = str_replace('&amp;', '&', $fieldvalue);

$fieldvalue = str_replace('&quot;', '"', $fieldvalue);

foreach (explode("\r\n", $value[4]) as $index1 => $value1) {

$value1 = str_replace("'", "&#039;", $value1);

$value1 = explode("|", $value1);

if( count($value1) < 2) $value1[1] = $value1[0];

$select .= "<option value=\"$index1\"" . ($fieldvalue == $value1[0] ? " selected" : "") . ">{$value1[1]}</option>\r\n";

}

$select .= "</select>";
 ```
 pastdagi kodga almashtiramiz:
```php
} elseif ($value[3] == "select") {
		
		if ($xfieldmode == "site") {
			$select = "<select name=\"xfield[$fieldname]\">";
		} else {
		    if($fieldname == 'country'){
		        $select = "<select class=\"uniform\" name=\"xfield[$fieldname][]\" multiple>";
		    }else{
		        $select = "<select class=\"uniform\" name=\"xfield[$fieldname]\">";    
		    }
		}
		
		if ( !isset($fieldvalue) ) $fieldvalue = "";

		$fieldvalue = str_replace('&amp;', '&', $fieldvalue);

        foreach (explode("\r\n", htmlspecialchars($value[4], ENT_QUOTES, $config['charset'] )) as $index1 => $value1) {

		  $value1 = explode("|", $value1);
		  if( count($value1) < 2) $value1[1] = $value1[0];
		  if($fieldname == 'country'){
		      $fieldvalue_array = explode(',',$fieldvalue);
		      $select .= "<option value=\"$index1\"" . (in_array($value1[0], $fieldvalue_array) ? " selected " : "") . ">{$value1[1]}</option>\r\n";
		  }else{
		       $select .= "<option value=\"$index1\"" . ($fieldvalue == $value1[0] ? " selected " : "") . ">{$value1[1]}</option>\r\n";   
		  }
        }

		$select .= "</select>";
```

 3. aynan shu faylning o'zida joylashgan `$options = explode("|", $options[$_POST['xfield'][$value[0]]] );` qatorini topamiz va qator doirasidagi kodni quyidagi holatdan

```php
if ($value[3] == "select") {
$options = explode("\r\n", $value[4]);
$options = explode("|", $options[$_POST['xfield'][$value[0]]] );
$postedxfields[$value[0]] = $options[0];
}
```
ushbu kodga almashtiramiz va faylni saqlaymiz.
```php
if ($value[3] == "select") {
                if($value[0] == 'country'){
                    $options = explode("\r\n", $value[4]);
                    $c_options = [];
                    $c_options_l = [];
                    foreach($options as $opt){
                        $opt = explode("|", $opt);
                        $c_options[] = $opt[0]; 
                    }
                    if(count($_POST['xfield'][$value[0]]) > 0){
                        foreach($_POST['xfield'][$value[0]] as $sc){
                            $c_options_l[] = $c_options[$sc];     
                        }
                    }
				    $postedxfields[$value[0]] = implode(',', $c_options_l);
                   
                }else{
                    $options = explode("\r\n", $value[4]);
				    $options = explode("|", $options[$_POST['xfield'][$value[0]]] );
		            $postedxfields[$value[0]] = $options[0];   
                }
                
		            
			}
```

Yuqoridagi kodlar tahrirlangach boshqaruv panelining ***Добавление новости*** yoki ***Редактирование публикаций*** bo'limiga qarasak `Mamlakatlar` maydoni va maydonda bir necha mamlakat tanlash imkoni mavjud bo'ladi.

4. `engine/modules` papkasidan `country.php` faylini yaratib uning ichiga quyidagilarni kiritamiz.

```php
<?php

include 'Sxgeo.php';

if ( !function_exists('geoCodeConvert') ) {
	
	function geoCodeConvert($geocode){
	    $country = array('Unknown country', 'Afghanistan', 'Åland Islands', 'Albania', 'Algeria', 'American Samoa', 'Andorra', 'Angola', 'Anguilla', 'Antarctica', 'Antigua and Barbuda',
	        'Argentina', 'Armenia', 'Aruba', 'Australia', 'Austria', 'Azerbaijan', 'Bahamas', 'Bahrain', 'Bangladesh', 'Barbados', 'Belarus', 'Belgium', 'Belize',
	        'Benin', 'Bermuda', 'Bhutan', 'Bolivia (Plurinational State of)', 'Bonaire', 'Bosnia and Herzegovina', 'Botswana', 'Bouvet Island', 'Brazil',
	        'British Indian Ocean Territory', 'Brunei Darussalam', 'Bulgaria', 'Burkina Faso', 'Burundi', 'Cambodia', 'Cameroon', 'Canada', 'Cabo Verde',
	        'Cayman Islands', 'Central African Republic', 'Chad', 'Chile', 'China', 'Christmas Island', 'Cocos (Keeling) Islands', 'Colombia', 'Comoros',
	        'Congo', 'Congo (Democratic Republic of the)', 'Cook Islands', 'Costa Rica', 'Côte d`Ivoire', 'Croatia', 'Cuba', 'Curaçao', 'Cyprus', 'Czech Republic',
	        'Denmark', 'Djibouti', 'Dominica', 'Dominican Republic', 'Ecuador', 'Egypt', 'El Salvador', 'Equatorial Guinea', 'Eritrea', 'Estonia', 'Ethiopia',
	        'Falkland Islands (Malvinas)', 'Faroe Islands', 'Fiji', 'Finland', 'France', 'French Guiana', 'French Polynesia', 'French Southern Territories',
	        'Gabon', 'Gambia', 'Georgia', 'Germany', 'Ghana', 'Gibraltar', 'Greece', 'Greenland', 'Grenada', 'Guadeloupe', 'Guam', 'Guatemala', 'Guernsey', 'Guinea',
	        'Guinea-Bissau', 'Guyana', 'Haiti', 'Heard Island and McDonald Islands', 'Holy See', 'Honduras', 'Hong Kong', 'Hungary', 'Iceland', 'India', 'Indonesia',
	        'Iran (Islamic Republic of)', 'Iraq', 'Ireland', 'Isle of Man', 'Israel', 'Italy', 'Jamaica', 'Japan', 'Jersey', 'Jordan', 'Kazakhstan', 'Kenya',
	        'Kiribati', 'Korea (Democratic People`s Republic of)', 'Korea (Republic of)', 'Kuwait', 'Kyrgyzstan', 'Lao People`s Democratic Republic',
	        'Latvia', 'Lebanon', 'Lesotho', 'Liberia', 'Libya', 'Liechtenstein', 'Lithuania', 'Luxembourg', 'Macao', 'Macedonia', 'Madagascar', 'Malawi',
	        'Malaysia', 'Maldives', 'Mali', 'Malta', 'Marshall Islands', 'Martinique', 'Mauritania', 'Mauritius', 'Mayotte', 'Mexico', 'Micronesia (Federated States of)',
	        'Moldova (Republic of)', 'Monaco', 'Mongolia', 'Montenegro', 'Montserrat', 'Morocco', 'Mozambique', 'Myanmar', 'Namibia', 'Nauru', 'Nepal', 'Netherlands',
	        'New Caledonia', 'New Zealand', 'Nicaragua', 'Niger', 'Nigeria', 'Niue', 'Norfolk Island', 'Northern Mariana Islands', 'Norway', 'Oman', 'Pakistan',
	        'Palau', 'Palestine', 'Panama', 'Papua New Guinea', 'Paraguay', 'Peru', 'Philippines', 'Pitcairn', 'Poland', 'Portugal', 'Puerto Rico', 'Qatar', 'Réunion',
	        'Romania', 'Russian Federation', 'Rwanda', 'Saint Barthélemy', 'Saint Helena', 'Saint Kitts and Nevis', 'Saint Lucia', 'Saint Martin (French part)',
	        'Saint Pierre and Miquelon', 'Saint Vincent and the Grenadines', 'Samoa', 'San Marino', 'Sao Tome and Principe', 'Saudi Arabia', 'Senegal', 'Serbia',
	        'Seychelles', 'Sierra Leone', 'Singapore', 'Sint Maarten (Dutch part)', 'Slovakia', 'Slovenia', 'Solomon Islands', 'Somalia', 'South Africa',
	        'South Georgia and the South Sandwich Islands', 'South Sudan', 'Spain', 'Sri Lanka', 'Sudan', 'Suriname', 'Svalbard and Jan Mayen', 'Swaziland',
	        'Sweden', 'Switzerland', 'Syrian Arab Republic', 'Taiwan (Province of China)', 'Tajikistan', 'Tanzania', 'Thailand', 'Timor-Leste', 'Togo', 'Tokelau',
	        'Tonga', 'Trinidad and Tobago', 'Tunisia', 'Turkey', 'Turkmenistan', 'Turks and Caicos Islands', 'Tuvalu', 'Uganda', 'Ukraine', 'United Arab Emirates',
	        'United Kingdom of Great Britain and Northern Ireland', 'United States of America', 'United States Minor Outlying Islands', 'Uruguay', 'Uzbekistan',
	        'Vanuatu', 'Venezuela (Bolivarian Republic of)', 'Viet Nam', 'Virgin Islands (British)', 'Virgin Islands (U.S.)', 'Wallis and Futuna', 'Western Sahara',
	        'Yemen', 'Zambia', 'Zimbabwe');

	    $alfa2 = array('XX', 'AF', 'AX', 'AL', 'DZ', 'AS', 'AD', 'AO', 'AI', 'AQ', 'AG', 'AR', 'AM', 'AW', 'AU', 'AT', 'AZ', 'BS', 'BH', 'BD', 'BB', 'BY', 'BE', 'BZ', 'BJ', 'BM',
	        'BT', 'BO', 'BQ', 'BA', 'BW', 'BV', 'BR', 'IO', 'BN', 'BG', 'BF', 'BI', 'KH', 'CM', 'CA', 'CV', 'KY', 'CF', 'TD', 'CL', 'CN', 'CX', 'CC', 'CO', 'KM', 'CG', 'CD',
	        'CK', 'CR', 'CI', 'HR', 'CU', 'CW', 'CY', 'CZ', 'DK', 'DJ', 'DM', 'DO', 'EC', 'EG', 'SV', 'GQ', 'ER', 'EE', 'ET', 'FK', 'FO', 'FJ', 'FI', 'FR', 'GF', 'PF', 'TF',
	        'GA', 'GM', 'GE', 'DE', 'GH', 'GI', 'GR', 'GL', 'GD', 'GP', 'GU', 'GT', 'GG', 'GN', 'GW', 'GY', 'HT', 'HM', 'VA', 'HN', 'HK', 'HU', 'IS', 'IN', 'ID', 'IR', 'IQ',
	        'IE', 'IM', 'IL', 'IT', 'JM', 'JP', 'JE', 'JO', 'KZ', 'KE', 'KI', 'KP', 'KR', 'KW', 'KG', 'LA', 'LV', 'LB', 'LS', 'LR', 'LY', 'LI', 'LT', 'LU', 'MO', 'MK', 'MG',
	        'MW', 'MY', 'MV', 'ML', 'MT', 'MH', 'MQ', 'MR', 'MU', 'YT', 'MX', 'FM', 'MD', 'MC', 'MN', 'ME', 'MS', 'MA', 'MZ', 'MM', 'NA', 'NR', 'NP', 'NL', 'NC', 'NZ', 'NI',
	        'NE', 'NG', 'NU', 'NF', 'MP', 'NO', 'OM', 'PK', 'PW', 'PS', 'PA', 'PG', 'PY', 'PE', 'PH', 'PN', 'PL', 'PT', 'PR', 'QA', 'RE', 'RO', 'RU', 'RW', 'BL', 'SH', 'KN',
	        'LC', 'MF', 'PM', 'VC', 'WS', 'SM', 'ST', 'SA', 'SN', 'RS', 'SC', 'SL', 'SG', 'SX', 'SK', 'SI', 'SB', 'SO', 'ZA', 'GS', 'SS', 'ES', 'LK', 'SD', 'SR', 'SJ', 'SZ',
	        'SE', 'CH', 'SY', 'TW', 'TJ', 'TZ', 'TH', 'TL', 'TG', 'TK', 'TO', 'TT', 'TN', 'TR', 'TM', 'TC', 'TV', 'UG', 'UA', 'AE', 'GB', 'US', 'UM', 'UY', 'UZ', 'VU', 'VE',
	        'VN', 'VG', 'VI', 'WF', 'EH', 'YE', 'ZM', 'ZW');

	    $alfa3 = array('XXX', 'AFG', 'ALA', 'ALB', 'DZA', 'ASM', '_AND', 'AGO', 'AIA', 'ATA', 'ATG', 'ARG', 'ARM', 'ABW', 'AUS', 'AUT', 'AZE', 'BHS', 'BHR', 'BGD', 'BRB', 'BLR',
	        'BEL', 'BLZ', 'BEN', 'BMU', 'BTN', 'BOL', 'BES', 'BIH', 'BWA', 'BVT', 'BRA', 'IOT', 'BRN', 'BGR', 'BFA', 'BDI', 'KHM', 'CMR', 'CAN', 'CPV', 'CYM', 'CAF', 'TCD',
	        'CHL', 'CHN', 'CXR', 'CCK', 'COL', 'COM', 'COG', 'COD', 'COK', 'CRI', 'CIV', 'HRV', 'CUB', 'CUW', 'CYP', 'CZE', 'DNK', 'DJI', 'DMA', 'DOM', 'ECU', 'EGY', 'SLV',
	        'GNQ', 'ERI', 'EST', 'ETH', 'FLK', 'FRO', 'FJI', 'FIN', 'FRA', 'GUF', 'PYF', 'ATF', 'GAB', 'GMB', 'GEO', 'DEU', 'GHA', 'GIB', 'GRC', 'GRL', 'GRD', 'GLP', 'GUM',
	        'GTM', 'GGY', 'GIN', 'GNB', 'GUY', 'HTI', 'HMD', 'VAT', 'HND', 'HKG', 'HUN', 'ISL', 'IND', 'IDN', 'IRN', 'IRQ', 'IRL', 'IMN', 'ISR', 'ITA', 'JAM', 'JPN', 'JEY',
	        'JOR', 'KAZ', 'KEN', 'KIR', 'PRK', 'KOR', 'KWT', 'KGZ', 'LAO', 'LVA', 'LBN', 'LSO', 'LBR', 'LBY', 'LIE', 'LTU', 'LUX', 'MAC', 'MKD', 'MDG', 'MWI', 'MYS', 'MDV',
	        'MLI', 'MLT', 'MHL', 'MTQ', 'MRT', 'MUS', 'MYT', 'MEX', 'FSM', 'MDA', 'MCO', 'MNG', 'MNE', 'MSR', 'MAR', 'MOZ', 'MMR', 'NAM', 'NRU', 'NPL', 'NLD', 'NCL', 'NZL',
	        'NIC', 'NER', 'NGA', 'NIU', 'NFK', 'MNP', 'NOR', 'OMN', 'PAK', 'PLW', 'PSE', 'PAN', 'PNG', 'PRY', 'PER', 'PHL', 'PCN', 'POL', 'PRT', 'PRI', 'QAT', 'REU', 'ROU',
	        'RUS', 'RWA', 'BLM', 'SHN', 'KNA', 'LCA', 'MAF', 'SPM', 'VCT', 'WSM', 'SMR', 'STP', 'SAU', 'SEN', 'SRB', 'SYC', 'SLE', 'SGP', 'SXM', 'SVK', 'SVN', 'SLB', 'SOM',
	        'ZAF', 'SGS', 'SSD', 'ESP', 'LKA', 'SDN', 'SUR', 'SJM', 'SWZ', 'SWE', 'CHE', 'SYR', 'TWN', 'TJK', 'TZA', 'THA', 'TLS', 'TGO', 'TKL', 'TON', 'TTO', 'TUN', 'TUR',
	        'TKM', 'TCA', 'TUV', 'UGA', 'UKR', 'ARE', 'GBR', 'USA', 'UMI', 'URY', 'UZB', 'VUT', 'VEN', 'VNM', 'VGB', 'VIR', 'WLF', 'ESH', 'YEM', 'ZMB', 'ZWE');

	    $numeric = array('000', '004', '248', '008', '012', '016', '020', '024', '660', '010', '028', '032', '051', '533', '036', '040', '031', '044', '048', '050', '052', '112',
	        '056', '084', '204', '060', '064', '068', '535', '070', '072', '074', '076', '086', '096', '100', '854', '108', '116', '120', '124', '132', '136', '140', '148',
	        '152', '156', '162', '166', '170', '174', '178', '180', '184', '188', '384', '191', '192', '531', '196', '203', '208', '262', '212', '214', '218', '818', '222',
	        '226', '232', '233', '231', '238', '234', '242', '246', '250', '254', '258', '260', '266', '270', '268', '276', '288', '292', '300', '304', '308', '312', '316',
	        '320', '831', '324', '624', '328', '332', '334', '336', '340', '344', '348', '352', '356', '360', '364', '368', '372', '833', '376', '380', '388', '392', '832',
	        '400', '398', '404', '296', '408', '410', '414', '417', '418', '428', '422', '426', '430', '434', '438', '440', '442', '446', '807', '450', '454', '458', '462',
	        '466', '470', '584', '474', '478', '480', '175', '484', '583', '498', '492', '496', '499', '500', '504', '508', '104', '516', '520', '524', '528', '540', '554',
	        '558', '562', '566', '570', '574', '580', '578', '512', '586', '585', '275', '591', '598', '600', '604', '608', '612', '616', '620', '630', '634', '638', '642',
	        '643', '646', '652', '654', '659', '662', '663', '666', '670', '882', '674', '678', '682', '686', '688', '690', '694', '702', '534', '703', '705', '090', '706',
	        '710', '239', '728', '724', '144', '729', '740', '744', '748', '752', '756', '760', '158', '762', '834', '764', '626', '768', '772', '776', '780', '788', '792',
	        '795', '796', '798', '800', '804', '784', '826', '840', '581', '858', '860', '548', '862', '704', '092', '850', '876', '732', '887', '894', '716');


	    if (ctype_digit((string) $geocode)) {
	        $key = array_search($geocode, $numeric);
	    } elseif (mb_strlen($geocode, "UTF-8") == 2) {
	        $key = array_search($geocode, $alfa2);
	    } elseif (mb_strlen($geocode, "UTF-8") == 3) {
	        $key = array_search($geocode, $alfa3);
	    } else {
	        $key = array_search($geocode, $country);
	    }

	    if ($key) {
	        return array('geo_country' => $country[$key], 'geo_alfa2' => $alfa2[$key], 'geo_alfa3' => $alfa3[$key], 'geo_numeric' => $numeric[$key]);
	    }

	    return array('geo_country' => 'Unknown country', 'geo_alfa2' => 'XX', 'geo_alfa3' => 'XXX', 'geo_numeric' => '000');
	}
}

if ( !function_exists('getCountryPermission') ) {
	function getCountryPermission($clist='') {
		if ($clist == '') return TRUE;
		$clist = explode(',', $clist);
		$SxGeo = new SxGeo();
		$ip = getUserIp();
		$country = $SxGeo->getCountry($ip);
		$country = geoCodeConvert($country);
		unset($SxGeo);
		if (in_array($country['geo_alfa3'], $clist)) {
			return TRUE;
		}else{
			return FALSE;
		}
	}
}

if ( !function_exists('getUserIp') ) {
	function getUserIp() {
		$serverVars = $_SERVER;
    	$searchList = "HTTP_CLIENT_IP,HTTP_X_FORWARDED_FOR,HTTP_X_FORWARDED,HTTP_X_CLUSTER_CLIENT_IP,HTTP_FORWARDED_FOR,HTTP_FORWARDED,REMOTE_ADDR";
    	$clientIpAddress = "";

    	$mylist = explode(',', $searchList);
    	foreach ($mylist as $myItem) {
        	if (isset($serverVars[trim($myItem)])) {
            	$myIpList = explode(',', $serverVars[trim($myItem)]);
            	foreach ($myIpList as $myIp) {
                	if (filter_var(trim($myIp), FILTER_VALIDATE_IP)) {
                    	$clientIpAddress = trim($myIp);
                    	break;
                	}
            	}
        	}

        	if (trim($clientIpAddress) != "") break;
    	}

    	if (trim($clientIpAddress) == "") {
      		$clientIpAddress = "Unknown";
    	}

    	return $clientIpAddress;
	}
}
```

4. `engine/modules` papkasiga ushbu linkdagi [sxgeo.zip]({contents_url="blog/datalife-engine-postlarini-mamlakatlar-boyicha-boshqarish/sxgeo.zip"}) faylini yuklab olib arxiv ichidagilarni papkaga joylaymiz.

5. `engine/modules/main.php` faylining quyi qismidan `echo $tpl->result['main'];` qatorini topib quyidagilarga almashtiramiz.
```php
include_once $_SERVER['DOCUMENT_ROOT'].'/engine/modules/country.php';
//echo $tpl->result['main'];
eval (' ?' . '>' . $main . '<' . '?php ');
```
Tizim mamlakatlar oralig'ida boshqarishga tayyor faqatgina shablon qismimizga bir ikki o'zgartirishlar kirisak bo'lgani.

6. `fullstrory.tpl` faylining eng yuqori qismiga quyidagi kodni kiritamiz.

```php
<?php
	if( !getCountryPermission('[xfvalue_country]') ){
		@header( "Location: /error.html" );
	}
?>
```

Ushbu kod agarda post kerakli mamlakat doirasida bo'lmasa foydalanuvchini `error.html` sahifasiga yo'naltiradi. Tabga ko'ra kodni yana o'z tizimingizga moslashingiz mumkin.

7. `shortstory.tpl` faylining eng yuqori qismiga quyidagi kodni joylaymiz
```php
<?php
	if( getCountryPermission('[xfvalue_country]') ){
?>
```

eng quyi qismiga esa quyidagicha:
```php
<?php
	}
?>
```

Ushbu kod postlar ro'yxatida mamlakatga daxlsiz bo'lgan postni chiqarmaslik imkonini yaratadi.

8. Tizim ishga tayyor. Boshqaruv panelidan istalgan postni qo'shish yoki tahrirlash jarayonida kerakli mamlakatlarni tanlasangiz post faqat o'sha mamlakatlardagina ko'rinadi. Agarda hech bir mamlakat kiritilmasa post barcha mamlakatlarda teng ravishda chiqadi.