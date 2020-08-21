# HYAS Insight

![HYAS](https://www.hyas.com/hubfs/logo-1.svg "HYAS")
HYAS Insight provides On-Demand Enrichment of Passive DNS, Dynamic DNS, Passive Hash, SSL Certificate, Device Geo (Mobile Geolocation), Sinkhole, and Whois endpoints using the HYAS Insight enrichment API source.

<br>

 This connector is available in the following products and regions:

 | Service | Class | Regions |
 | ------ | ------ | ------ |
 | Logic Apps | Standard | All [Logic Apps regions](https://azure.microsoft.com/en-us/global-infrastructure/services/?products=logic-apps&regions=all) except the following:<br>-Azure Government regions<br>-Azure China regions |
 | Power Automate | Premium | All [Power Automate regions](https://docs.microsoft.com/en-us/power-automate/regions-overview) except the following:<br>-US Government (GCC)<br>-US Government (GCC High)<br>-China Cloud operated by 21Vianet |
 | Power Apps | Premium | All [Power Apps regions](https://docs.microsoft.com/en-us/power-platform/admin/regions-overview#what-regions-are-available) except the following:<br>-US Government (GCC)<br>-US Government (GCC High)<br>-China Cloud operated by 21Vianet |

<br>

## Pre-requisites
To use this integration, you need to have a HYAS Insight API Key provisioned by HYAS Infosec Inc to authenticate requests to HYAS Insight API.

<br>

## Creating a connection
To connect your account, you will need the following information:

| Name | Type | Description
 | ------ | ------ | ------ |
 | X-API-Key | securestring | The X-API-Key for this api |
  
<br>

 ## Throttling Limits
 | Name | Calls | Renewal Period
 | ------ | ------ | ------ |
 | API calls per connection | 100 | 60 Seconds |
 
<br>

  
 ## Actions:
 | Action Name | Description
  | ------ | ------ |
  | [Retrieve Passive DNS Information for Domain or IP Address](#retrieve-passive-dns-information-for-domain-or-ip-address) |  Retrieve on demand Passive DNS enrichment data for Domain or IP Address |
  | [Retrieve Whois Information for Domain or Email Address or Phone Number](#retrieve-whois-information-for-domain-or-email-address-or-phone-number) | Retrieve on demand Whois enrichment data for Domain or Email Address or PhoneNumber |
  | [Retrieve Dynamic DNS Information for IP Address or Email Address](#retrieve-dynamic-dns-information-for-ip-address-or-email-address) | Retrieve on demand Dynamic DNS enrichment data for IP Address or Email Address |
  | [Retrieve Passive Hash Information for IP Address](#retrieve-passive-hash-information-for-ip-address) |Retrieve on demand Passive Hash enrichment data for IP Address |
| [Retrieve Sinkhole Information for IP Address](#retrieve-sinkhole-information-for-ip-address) | Retrieve on demand Sinkhole enrichment data for IP Address |
  | [Retrieve Device Geo Information for IP Address](#retrieve-device-geo-information-for-ip-address) | Retrieve on demand Device Geo enrichment data for IP Address |
 | [Retrieve SSL Certificate Information for IP Address](#retrieve-ssl-certificate-information-for-ip-address) | Retrieve on demand SSL Certificate enrichment data for IP Address |

<br>

### Retrieve Passive DNS Information for Domain or IP Address

Operation ID: PASSIVE_DNS

Retrieve on demand Passive DNS enrichment data for Domain or IP Address

#### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | Domain | domain | True | String | Domain you want to enrich |
 | IP Address | ipv4 | True | String | IP Address you want to enrich |


#### Returns
##### **Body** : [PassiveDNSResults](#passivednsresults)

<br>


### Retrieve Whois Information for Domain or Email Address or Phone Number

Operation ID: WHOIS

Retrieve on demand Whois enrichment data for Domain or Email Address or Phone Number

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | Domain | domain | True | String | Domain you want to enrich |
 | Email Address | email | True | String | Email Address you want to enrich |
 | Phone Number | phone | True | String | Phone Number you want to enrich |

 #### Returns
##### **Body** : [WhoisResult](#whoisresult)

<br>

### Retrieve Dynamic DNS Information for IP Address or Email Address

Operation ID: DYNAMIC_DNS

Retrieve on demand Dynamic DNS enrichment data for IP Address or Email Address

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | IP Address | ipv4 | True | String | IP Address you want to enrich |
 | Email Address | email | True | String |Email Address you want to enrich |

  #### Returns
##### **Body** :  [DynamicDNSResult](#dynamicdnsresult)

<br>

### Retrieve Passive Hash Information for IP Address 

Operation ID: PASSIVE_HASH
Retrieve on demand Passive Hash enrichment data for IP Address

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | IP Address | ipv4 | True | String | IP Address you want to enrich |

 #### Returns
##### **Body** : [passiveHashResult](#passivehashresult)

<br>

 ### Retrieve Sinkhole Information for IP Address

Operation ID: SINKHOLE

Retrieve on demand Sinkhole enrichment data for IP Address

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | IP Address | ipv4 | True | String | IP Address you want to enrich |

 #### Returns
##### **Body** :  [SinkholeResult](#sinkholeresult)

<br>

### Retrieve Device Geo Information for IP Address

Operation ID: DEVICE_GEO

Retrieve on demand Device Geo enrichment data for IP Address

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | IPv4 Address | ipv4 | True | String | IPv4 Address you want to enrich |
 | IPv6 Address | ipv6 | True | String | IPv6 Address you want to enrich |

 #### Returns
##### **Body** :  [DeviceGeoResult](#devicegeoresult)

<br>

### Retrieve SSL Certificate Information for IP Address

 Operation ID: SSL_CERTIFICATE

Retrieve on demand SSL Certificate enrichment data for IP Address

 #### Parameters

 | Name | Key | Required | Type | Description
 | ------ | ------ | ------ | ------ | ------ |
 | IP Address | ipv4 | True | String | IP Address you want to enrich |
 
 #### Returns
##### **Body** : [SSLCertificateResult](#sslcertificateresult)

<br>


### PassiveDNSResults

| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
| cert_name | cert_name | String | The certificate name for passive DNS record
|count | count | String | The passive DNS count |
|domain| domain | String | The domain of the passive DNS information requested |
|first_seen | first_seen | String | The first time this domain was seen 
|city_name | ip.geo.city_name | String | The city name for the domain's IP address |
|country_iso_code | ip.geo.country_iso_code | String | The country ISO code for the domain's IP address |
|country_name | ip.geo.country_name | String | The country name for the domain's IP address |
|location_latitude | ip.geo.location_latitude | String | The location latitude for the domain's IP address |
|location_longitude | ip.geo.location_longitude | String | The location longitude for the domain's IP address |
|postal_code | ip.geo.postal_code | String | The postal code for the domain's IP address |
|ip | ip.ip | String | The IP address for the domain |
|autonomous_system_number | ip.isp.autonomous_system_number | String | The Autonomous System Number(ASN) for the domain's ISP |
|autonomous_system_organization | ip.isp.autonomous_system_organization | String | The Autonomous System Organization for the domain's ISP |
|ip_address | ip.isp.ip_address | String | The IP Address for the domain's ISP
|isp | ip.isp.isp | String | The ISP of the domain |
|organization | ip.isp.organization | String |The ISP organization of the domain |
|ipv4 | ipv4 | String | The ipv4 address of the passive DNS record |
|ipv6 | ipv6 | String | The ipv6 address of the passive DNS record |
|last_seen | last_seen | String | The last time this domain was seen |
|sha1 | sha1 | String | The sha1 sum of the passive DNS  record |
|sources | sources | String Array | sources Information |

<br>


### WhoIsResult
| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
|address | address | String Array | Address Information |
|city | city | String Array |  The city of the registrant |
|country | country | String Array | The country of the registrant |
|data | data | String |  Data Information |
|datetime | datetime | String |  Date Time Information |
|domain | domain | String |  The domain of the registrant |
|domain_2tld | domain_2tld | String | The second-level domain of the registrant |
|domain_created_datetime | domain_created_datetime | String | The date and time when the Whois record was created |
|domain_expires_datetime | domain_expires_datetime | String | The date and time when the Whois record expires |
|domain_updated_datetime | domain_updated_datetime | String | The date and time when the Whois record was last updated |
|email | email | String Array | Email Information |
|idn_name | idn_name | String | The international domain name |
|meta_data | meta_data | String | The metadata information |
|name | name | String Array | The contact name (registrant contact, administrative contact, technical contact, or abuse contact) |
|nameserver | nameserver | String Array |  The nameserver domain |
|phone | phone.phone | String |  The phone number of the registrant in e164 format |
|carrier | phone.phone_info.carrier | String |  The phone number carrier Information |
|country | phone.phone_info.country | String |  The phone number Country Information |
|geo | phone.phone_info.geo | String |  The phone number geo Information |
|privacy_punch | privacy_punch | Boolean |
|registrar | registrar | String |  The domain registrar |
|whois_hash | whois_hash | String |  Hash Information |
|whois_id | whois_id | String |  Id Information |

<br>


### DynamicDNSResult
| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
|a_record | a_record | String | The A record for the domain |
|account | account | String | The account holder name |
|created | created | String |The date which the domain was created |
|created_ip | created_ip | String | The IP address of the account holder |
|domain | domain | String |The domain associated with the Dynamic DNS information |
|domain_creator_ip | domain_creator_ip | String | The IP address of the domain creator |
|email | email | String | The email address connected to the domain |

<br>


### PassiveHashResult
| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
|domain | domain | String | The domain of the passive hash information requested |
|md5_count | md5_count | String | MD5 hash count |

<br>


### SinkholeResult
| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
|count | count | String | The sinkhole counts |
|country_name | country_name | String | The country of the IP |
|data_port | data_port | String | The data port |
|datetime | datetime | String | The first seen date of the sinkhole |
|ipv4 | ipv4 | String |  The ipv4 of the sinkhole |
|last_seen | last_seen | String | The last seen date of the sinkhole |
|organization_name | organization_name | String | The ISP organization for the IP |
|sink_source | sink_source | String | The ipv4 of the sink source |

<br>


### DeviceGeoResult
| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
|datetime | datetime | String | A date-time string in RFC 3339 format |
|device_geo_id | device_geo_id | String | Geolocation ID |
|device_user_agent | device_user_agent | String | The user agent for the device |
|geo_country_alpha_2 | geo_country_alpha_2 | String | The ISO 3316 alpha-2 code for the country associated with the latitude/longitude reported |
|geo_horizontal_accuracy | geo_horizontal_accuracy | String | Geolocation accuracy Information |
|ipv4 | ipv4 | String | The ipv4 address assigned to the device. A device may have either or ipv4 and ipv6 |
|ipv6 | ipv6 | String | The ipv4 address assigned to the device. A device may have either or ipv4 and ipv6 |
|latitude | latitude | number | Units are degrees on the WGS 84 spheroid |
|longitude | longitude | number | Units are degrees on the WGS 84 spheroid |
|wifi_bssid | wifi_bssid | String | The BSSID (MAC address) of the WIFI router that the device communicated through |
|wifi_ssid | wifi_ssid | String | The SSID (name) of the WIFI network that the device communicated through |

<br>


### SSLCertificateResult
| Name | Path | Type | Description
| ------ | ------ | ------ | ------ |
|related_count | related_count | String | The number of IP addresses connected to this certificate |
|ip | ssl_certs.ip | String | The IP address associated with certificate |
|cert_key | ssl_certs.ssl_cert.cert_key | String | The certificate key (sha1) |
|expire_date | ssl_certs.ssl_cert.expire_date | String |The expiry date of the certificate |
|issue_date | ssl_certs.ssl_cert.issue_date | String | The issue date of the certificate |
|issuer_commonName | ssl_certs.ssl_cert.issuer_commonName | String |The common name that the certificate was issued from |
|issuer_countryName | ssl_certs.ssl_cert.issuer_countryName | String | The country the certificate was issued from |
|issuer_localityName | ssl_certs.ssl_cert.issuer_localityName | String | The city where the issuer company is legally located |
|issuer_organizationName | ssl_certs.ssl_cert.issuer_organizationName | String |  The organization name that issued the certificate |
|issuer_organizationalUnitName| ssl_certs.ssl_cert.issuer_organizationalUnitName | String |  The organization name that issued the certificate |
|issuer_stateOrProvinceName | ssl_certs.ssl_cert.issuer_stateOrProvinceName | String | The state or province where the issuer company is legally located |
|md5 | ssl_certs.ssl_cert.md5 | String | SSL certificate MD5 Hash |
|serial_number | ssl_certs.ssl_cert.serial_number |  String | SSL certificate Serial Number |
|sha1 | ssl_certs.ssl_cert.sha1 | String |  SSL certificate SHA1 Hash |
|sha_256 | ssl_certs.ssl_cert.sha_256 | String | SSL certificate SHA 256 Hash |
|sig_algo | ssl_certs.ssl_cert.sig_algo | String | SSL certificate signing algorithm |
|signature | ssl_certs.ssl_cert.signature | String Array | SSL certificate signature |
|ssl_version | ssl_certs.ssl_cert.ssl_version | String | SSL Version Information |
|subject_commonName | ssl_certs.ssl_cert.subject_commonName | String |  The subject name that the certificate was issued to |
|subject_countryName | ssl_certs.ssl_cert.subject_countryName | String | The country the certificate was issued to |
|subject_localityName | ssl_certs.ssl_cert.subject_localityName | String |  The city where the subject company is legally located |
|subject_organizationName | ssl_certs.ssl_cert.subject_organizationName |  String | The organization name that received the certificate
|subject_organizationalUnitName | |ssl_certs.ssl_cert.subject_organizationalUnitName |  String | The organization name that received the certificate |
|subject_stateOrProvinceName | ssl_certs.ssl_cert.subject_stateOrProvinceName | String | The state or province name where the subject company is located |
|timestamp | ssl_certs.ssl_cert.timestamp |  String | Time Stamp Information |
