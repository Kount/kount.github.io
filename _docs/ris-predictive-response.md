---
title:
tags:
---

Predictive Response is a mechanism that can be used by Kount merchants to submit test requests and receive back predictable RIS responses. This means that a merchant, in order to test RIS, can generate a particular request that is designed to provide one or more specific RIS responses and/or errors. The predictive response inquiries are not actual RIS inquiries, which means the data will never be submitted to the database and will not be displayed in the Agent Web Console.

The primary reason for having Predictive Response functionality is to diagnose error responses being received from RIS. For instance, a merchant may receive a large number of different error codes after submitting a RIS request. Most of these errors can be reliably reproduced by passing malformed, missing, or additional data in the RIS request. However, some of the errors are extremely difficult or even impossible to reproduce through simple means. There is no way to re-create these errors in a systematic or predictable fashion using RIS request input, rules, and/or Data Collector.

In addition, the merchant may wish to invoke a specific response in order to understand how their respective OMS will manage certain responses or data returned in the response. Predictive Response allows merchants to submit requests designed to return exact responses including errors. An example would be if a merchant wanted to submit a RIS request that would return the very specific responses SCOR=71, AUTO=E, and GEOX=CA.

Predictive Responses are created using the UDF (User Defined Fields) override option. These User Defined Fields do not need to be created through the Agent Web Console, they can be simply passed in as additional fields in the Predictive Response RIS inquiry.

To create a Predictive Response RIS Inquiry, the request must contain a specific email parameter in the EMAL field: predictive@kount.com. Note: This email address is case sensitive and must be all lower case letters.

All other elements of the RIS request you submit must be valid elements and contain the minimum set of
required RIS keys.

##### Below is the hard coded default reply:

--- bash
‘TRAN’ => ‘6V100HV36D98’, ‘AUTO’ => ‘A’,
‘SCOR’ => 50,
‘GEOX’ => ‘US’,
‘BRND’ => ‘VISA’,
‘REGN’ => ‘US_ID’,
‘NETW’ => ‘A’, ‘CARDS’ => 2,
‘DEVICES’ => 1,
‘EMAILS’ => 3,
---
