---
title: RIS Payment Types
tags:
---

Kount supports multiple payment types. Depending on the payment type chosen by the customer, certain payment tokens are required. If the **PayPal Payer ID** or **Google Checkout Account ID** is not sent in the inquiry mode, then it must be sent in the update mode related to the transaction - otherwise the order details will not be displayed in the Agent Web Console.

Kount can add arbitrary payment types rapidly to support an international market. To view the current list of supported payment types, use the API endpoint:
https://api.kount.net/rpc/support/payments.html

See the API Specification Guide for further details. The content of the endpoint is generated in HTML but changing the extension to .XML or .JSON will produce content in those formats.
