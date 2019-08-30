---
title: API Enpoint Overview
subtitle: Restful API access will allow a merchant to programmatically interact with Kount via API, bypassing the Agent Web Console (AWC) completely.
tags: [API, Endpoints, Setup]
---

## Overview

Merchants have the ability to interact with Kount using Restful Application Programming Interfaces (APIs). Restful API access will allow a merchant to programmatically interact with Kount “under the hood” so to speak, bypassing the Agent Web Console (AWC) completely. These systems can be connected to an in-house interface so decisions can be made automatically.

If you request these services, Kount allows you to communicate with our application servers over the internet through a series of notifications and Restful API calls. APIs allow you to send information to Kount, such as adding a large number of email addresses to a VIP list, and receiving a response stating if your changes were successful.

## RESTful API Documentation

<a href="https://api.kount.net/rpc/list.html">click here.</a>


To obtain documentation regarding Kount's Restful API, <a href="https://api.kount.net/rpc/list.html">click here.</a> All of the following items are located within each Endpoint categorically.

* List of Endpoints
* Usage
* Error Codes 
* Response Samples
* Code Samples

## Error Codes 
In addition to the general three-digit error codes common with the Kount API endpoints, Kount offers four-digit error codes to provide additional information should a submission from a merchant encounter a problem. See below for a list of these codes. Note that the general format of an error message resembles the following example. In this sample response, the error is "1758 - Incomplete Transaction - Waiting for Update, try again later."

```
{"status":"failure","count":{"success":0,"failure":1},"errors":
[{"code":1758,"msg":"Incomplete transaction - waiting for update, try again later","scope":"AA000A0A0000","type":404}]}
```

##### General API
code: 2200 msg: Invalid merchant id
code: 2201 msg: Invalid status type
code: 2202 msg: Invalid address type
code: 2203 msg: Invalid tran/ordr ID
code: 2204 msg: Invalid agent email
code: 2205 msg: Order number returned multiple transactions
code: 2210 msg: Invalid user id

##### Transaction Report
code: 2220 msg: Invalid transaction report time offset
code: 2221 msg: Invalid transaction report time window

##### Category report
code: 2206 msg: Invalid category report type
code: 2207 msg: Invalid sorting order
code: 2208 msg: Invalid sorting column

##### RFCB (Refund/Chargeback)
code: 1725 msg: Invalid transaction id
code: 1731 msg: Transaction not found
code: 1743 msg: Invalid Refund/Chargeback status value, expects 'R' or 'C'
code: 1747 msg: Invalid reason
code: 1758 msg: Incomplete transaction - waiting for update, try again later
code: 1759 msg: Chargeback code too long, 50 characters maximum

##### General VIP
code: 1502 msg: Invalid review type
code: 1546 msg: Billing or Shipping indicator malformed
code: 1547 msg: Billing or Shipping indicator missing
code: 1560 msg: Invalid value - too long
code: 1561 msg: Required value was blank
code: 1562 msg: Unknown VIP type

##### VIP Card
code: 1508 msg: Invalid card number
code: 1520 msg: Card not found

##### VIP Email
code: 1501 msg: Invalid email format

##### VIP Device
code: 1504 msg: Invalid device id format
code: 1505 msg: Device id not found

##### VIP Address
code: 1509 msg: Address1 required
code: 1510 msg: Address1 too long, 256 characters maximum
code: 1511 msg: Address2 too long, 256 characters maximum
code: 1513 msg: City too long, 256 characters maximum
code: 1515 msg: State too long, 256 characters maximum
code: 1517 msg: Postal Code too long, 16 character maximum
code: 1545 msg: Country Code too long
code: 1550 msg: Address not found
code: 1551 msg: Malformed Address, expecting 7 delimited fields
code: 1552 msg: Email address not found when api passes in an address, the bill/ship code is not included.
code: 1553 msg: Malformed Address, expecting 6 delimited fields

##### VIP UDF (User Defined Fields)
code: 1571 msg: VIP UDF combination not found
code: 1572 msg: UDF label of type ALPHA-NUMERIC not found
code: 1573 msg: VIP UDF value must be 1-150 alpha-numeric characters
code: 1574 msg: Invalid VIP UDF input array

##### UDF (User Defined Fields)
code: 1540 msg: Label must be 1-28 alpha-numeric characters and begin with a letter
code: 1541 msg: Type must be NUMBER|ALPHA-NUMERIC|DATE|AMOUNT
code: 1543 msg: UDF already exists, cannot create
code: 1544 msg: Description must be 1-64 alpha-numeric characters
code: 1548 msg: ID must be 1-64 numeric characters
code: 1549 msg: Max number of supported UDFs reached

##### order status
code: 1702 msg: Invalid note or note too long

Misc
code: 9998 msg: Transaction has been modified by someone else
code: 9999 msg: Unknown error

