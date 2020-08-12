---
title: RIS Predictive Response - Test Environment
tags:
---

Predictive Response is a mechanism that can be used by Kount merchants to submit test requests and receive back predictable RIS responses. This means that a merchant, in order to test RIS, can generate a particular request that is designed to provide one or more specific RIS responses and/or errors. **The predictive response inquiries are not actual RIS inquiries, which means the data will never be submitted to the database and will not be displayed in the Agent Web Console.**

The primary reason for having Predictive Response functionality is to diagnose error responses being received from RIS. For instance, a merchant may receive a large number of different error codes after submitting a RIS request. Most of these errors can be reliably reproduced by passing malformed, missing, or additional data in the RIS request. However, some of the errors are extremely difficult or even impossible to reproduce through simple means. There is no way to re-create these errors in a systematic or predictable fashion using RIS request input, rules, and/or Data Collector.

In addition, the merchant may wish to invoke a specific response in order to understand how their respective OMS will manage certain responses or data returned in the response. Predictive Response allows merchants to submit requests designed to return exact responses including errors. An example would be if a merchant wanted to submit a RIS request that would return the very specific responses SCOR=71, AUTO=E, and GEOX=CA.

Predictive Responses are created using the UDF (User Defined Fields) override option. These User Defined Fields do not need to be created through the Agent Web Console, they can be simply passed in as additional fields in the Predictive Response RIS inquiry.

To create a Predictive Response RIS Inquiry, the request must contain a specific email parameter in the EMAL field: predictive@kount.com. Note: This email address is case sensitive and must be all lower case letters.

All other elements of the RIS request you submit must be valid elements and contain the minimum set of
required RIS keys.

##### Below is the hard coded default reply:
```
‘TRAN’ => ‘6V100HV36D98’, ‘AUTO’ => ‘A’,
‘SCOR’ => 50,
‘GEOX’ => ‘US’,
‘BRND’ => ‘VISA’,
‘REGN’ => ‘US_ID’,
‘NETW’ => ‘A’, ‘CARDS’ => 2,
‘DEVICES’ => 1,
‘EMAILS’ => 3,
‘VELO’ => 4,
‘VMAX’ => 4,
‘SITE’ => ‘DEFAULT’,
‘DEVICE_LAYERS’ => ‘D67BC18BAD.6EF0902E51.8C96FA9E7B.61FD602D96.940A6D1454’, ‘FINGERPRINT’ => ‘00482B9BED15A272730FCB590FFEBDDD’,
‘TIMEZONE’ => 420,
‘REGION’=> ‘ID’,
‘COUNTRY’=> ‘US’,
‘PROXY’ => ‘N’,
‘JAVASCRIPT’ => ‘Y’, ‘FLASH’ => ‘Y’,
‘COOKIES’ => ‘Y’,
‘HTTP_COUNTRY’ => ‘US’, ‘LANGUAGE’ => ‘EN’,
‘MOBILE_DEVICE’ => ‘N’, ‘MOBILE_TYPE’ => ‘’,
‘MOBILE_FORWARDER’ => ‘N’, ‘VOICE_DEVICE’ => ‘N’,
‘PC_REMOTE’ => ‘N’, ‘REASON_CODE’=> ‘’,
‘DDFS’ => ‘2013-07-19’, ‘DSR’ => ‘1080x1920’,
‘UAS’ => ‘Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.31 (KHTML, like Gecko) Chrome/26.0.1410.63 Safari/537.31’,
‘BROWSER’ => ‘Chrome 26.0.1410.63’, ‘OS’ => ‘Linux x86_64’,
‘PIP_IPAD’ => ‘’,
‘PIP_LAT’ => ‘’,
‘PIP_LON’ => ‘’,
‘PIP_COUNTRY’ => ‘’, ‘PIP_REGION’ => ‘’,
‘PIP_CITY’ => ‘’,
‘PIP_ORG’ => ‘’,
‘IP_IPAD’ => ‘10.0.0.1’,
‘IP_LAT’ => ‘43.6091’,
‘IP_LON’ => ‘-116.2097’, ‘IP_COUNTRY’ => ‘US’,
‘IP_REGION’ => ‘Idaho’, ‘IP_CITY’ => ‘Boise’,
‘IP_ORG’ => ‘Company Inc.’
```
To pass in a request that will result in a specific response, use one or more UDF overrides to trigger a mock RIS response.

The basic syntax is: UDF[~K!_label]=“foo”~K!_ is the prefix, label is the desired field for which you want a response, such as SCOR or ERRO, and after the equal sign (=), enter the specific value you want returned. The ~K!_ prefix is required to trigger the UDF to become a predictive response field.

##### Example 1 
You want to send in a request that will result in a Kount Score of 18, an Auto Decision of E, and a 601 System Error code.

###### Request: 
* UDF[~K!_SCOR]=18 
* UDF[~K!_AUTO]=E 
* UDF[~K!_ERRO]=601

###### Response: 
* SCOR=18 
* AUTO=E 
* ERRO=601

##### Example 2:
You want to pass in a request that will result in a Kount Score of 42, an Auto Decision of Decline and a GEOX of Nigeria.

###### Request: 
* UDF[~K!_SCOR]=42 
* UDF[~K!_AUTO]=D 
* UDF[~K!_GEOX]=NG

###### Response: 
* SCOR=42 
* AUTO=D 
* GEOX=NG

You can use UDF overrides to pass in an unlimited number of mock requests but all of the fields you pass in that are not overrides must be valid. In the response, all of the other elements, besides the UDF overrides will be the default values, including MODE and MERC.

