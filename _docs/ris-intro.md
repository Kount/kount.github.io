---
title: Risk Inquiry Service (RIS)
tags:
---

#### Sections in this page:
{:.no_toc}
* TOC
{:toc}

## Overview

The Risk Inquiry Service (RIS) joins device data provided from the data collector process with the customer order data sent from the merchant. Once the device data and the order data are combined, RIS evaluates and scores each transaction. After the evaluation, RIS returns a response string back to the merchant to be used by the merchant to approve, decline or hold the order for review. Each transaction will continue to be evaluated and dynamically scored for up to fourteen days. The following section describes how to implement the Risk Inquiry Service.

{% include image.html img="RISflowchart.png" lightbox="true" alt="Alt for image" caption="RIS Implementation" %}


### The following sequence describes the RIS process:

<ul class="uk-list uk-list-divider">
    <li>1.	Customer initiates purchase</li>
    <li>2.	Merchant initiates RIS request to Kount via HTTPS URL encoded post</li>
    <li>3.	Kount evaluates transaction</li>
    <li>4.	Kount returns evaluation response to merchant</li>
    <li>5.	Notification is displayed to customer</li>
</ul>

### Risk Inquiry Service Payment Types
Kount supports multiple payment types and depending upon the payment type chosen by the customer certain payment tokens are required. If the PayPal Payer ID or Google Checkout Account ID is not sent in the inquiry mode, then it must be sent in the update mode related to the transaction otherwise the order details will not be displayed in the Agent Web Console.

Kount can add arbitrary payment types rapidly to support an international market. To view the current list of supported payment types, use the API endpoint: (https://api.kount.net/rpc/support/payments.html)


### Risk Inquiry Service Requirments
RIS data posted to Kount must be URL encoded and submitted as key-value pairs. Much of the work can be simplified by utilizing a Kount provided SDK, including URL encoding. Kount provides a Software Development Kit (SDK) for Java, .NET, PHP, Perl, and Mobile environments.

Recommendations regarding each development environment and their supported versions, configuration, logging, and paths are found in the README file located in the “docs“ directory in each respective SDK, please read the documentation associated with each SDK.

1.	Port 443 must be available to post and receive data from Kount.
2.	API Keys are used to authenticate the RIS HTTPS submission to Kount, (similar to a password). A single API Key will be used for RIS submissions, the key is not subject to expiration date and does not require re-issuance. To generate an API Key, navigate to the ADMIN tab -> API Keys. See the RIS API Keys section of this document for more detailed instructions. Note: API Keys can only be used with Kount version 0630 and newer.
3.	SSL support is required for the RIS process. TLS version 1.2 is currently supported.
4.	The session identifier created during the data collector process must be passed as the session identifier for the RIS transaction. This identifier must be unique for at least 30 days. If a single session ID were to be used on multiple transactions, those transactions would link together and erroneously affect the persona information in the risk score.
5.	RIS posts are limited to a total of 40,960 characters or bytes.
6.	To utilize the various SDKs, several required static settings must be configured. Please refer to the README files included in each of the SDKs.
     * PHP settings.ini
     * .NET App.config
     * Python
     * Java All settings are included in inquiry
     
#### Required static settings found in the SDK: 

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;border-color:#ccc;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 20px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#fff;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 20px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#f0f0f0;}
.tg .tg-8421{font-size:15px;font-family:"Arial Black", Gadget, sans-serif !important;;background-color:#193d68;color:#f9f9f9;border-color:inherit;text-align:left;vertical-align:top}
.tg .tg-ds6z{font-size:15px;font-family:"Arial Black", Gadget, sans-serif !important;;background-color:#193d68;color:#f9f9f9;border-color:inherit;text-align:center;vertical-align:top}
.tg .tg-c3ow{border-color:inherit;text-align:center;vertical-align:top}
.tg .tg-abip{background-color:#f9f9f9;border-color:inherit;text-align:center;vertical-align:top}
.tg .tg-btxf{background-color:#f9f9f9;border-color:inherit;text-align:left;vertical-align:top}
.tg .tg-0pky{border-color:inherit;text-align:left;vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-ds6z">﻿Data</th>
    <th class="tg-ds6z">Size</th>
    <th class="tg-8421">Description</th>
    <th class="tg-ds6z">Example</th>
  </tr>
  <tr>
    <td class="tg-abip">Merchant_ID</td>
    <td class="tg-abip">6</td>
    <td class="tg-btxf">Six-digit identifier issued by Kount.</td>
    <td class="tg-abip">999999</td>
  </tr>
  <tr>
    <td class="tg-c3ow">COMPANY_SERVER_URL</td>
    <td class="tg-c3ow">N/A</td>
    <td class="tg-0pky">HTTPS URL path to the company’s servers provided in boarding documentation from Kount.</td>
    <td class="tg-c3ow">https://risk.test.kount.net</td>
  </tr>
  <tr>
    <td class="tg-abip">LOGGER</td>
    <td class="tg-abip">N/A</td>
    <td class="tg-btxf">Specifies which logger to use: SIMPLE or NOP.</td>
    <td class="tg-abip">SIMPLE</td>
  </tr>
  <tr>
    <td class="tg-c3ow">SIMPLE_LOG_LEVEL</td>
    <td class="tg-c3ow">N/A</td>
    <td class="tg-0pky">If SIMPLE logging is enabled, this lists logging levels in order of decreasing severity: FATAL, ERROR, WARN, INFO,DEBUG</td>
    <td class="tg-c3ow">WARN</td>
  </tr>
  <tr>
    <td class="tg-abip">SIMPLE_LOG_FILE</td>
    <td class="tg-abip">N/A</td>
    <td class="tg-btxf">Name of the log file for SIMPLE logging</td>
    <td class="tg-abip">company-sdk-ris.log</td>
  </tr>
  <tr>
    <td class="tg-c3ow">SIMPLE_LOG_PATH</td>
    <td class="tg-c3ow">N/A</td>
    <td class="tg-0pky">Path to where log file will be written. (Must be a valid path)</td>
    <td class="tg-c3ow">/some/path/to/log</td>
  </tr>
  <tr>
    <td class="tg-abip">APIKEY</td>
    <td class="tg-abip">Varies</td>
    <td class="tg-btxf">API Key value copied from clipboard - originating from API Key page within Agent Web Console</td>
    <td class="tg-abip">Alpha/Numeric hashed value provided by Kount</td>
  </tr>
  <tr>
    <td class="tg-c3ow">Client Certificate (deprecated field for legacy certificates)</td>
    <td class="tg-c3ow">N/A</td>
    <td class="tg-0pky">Depending on the SDK environment certain client certificate information will be required.</td>
    <td class="tg-c3ow">company-ris- certificate.p12</td>
  </tr>
</table>
