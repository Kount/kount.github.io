---
title: Risk Inquiry Service (RIS)
tags:
---

The Risk Inquiry Service (RIS) joins device data provided from the data collector process with the customer order data sent from the merchant. Once the device data and the order data are combined, RIS evaluates and scores each transaction. After the evaluation, RIS returns a response string back to the merchant to be used by the merchant to approve, decline or hold the order for review. Each transaction will continue to be evaluated and dynamically scored for up to fourteen days. The following section describes how to implement the Risk Inquiry Service.

The following sequence describes the RIS process:
1.	Customer initiates purchase
2.	Merchant initiates RIS request to Kount via HTTPS URL encoded post
3.	Kount evaluates transaction
4.	Kount returns evaluation response to merchant
5.	Notification is displayed to customer

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;border-color:#ccc;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 20px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#fff;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 20px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#f0f0f0;}
.tg .tg-8421{font-size:15px;font-family:"Arial Black", Gadget, sans-serif !important;;background-color:#193d68;color:#f9f9f9;border-color:inherit;text-align:left;vertical-align:top}
.tg .tg-btxf{background-color:#f9f9f9;border-color:inherit;text-align:left;vertical-align:top}
.tg .tg-0pky{border-color:inherit;text-align:left;vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-8421">﻿Data</th>
    <th class="tg-8421">Size</th>
    <th class="tg-8421">Description</th>
    <th class="tg-8421">Example</th>
  </tr>
  <tr>
    <td class="tg-btxf">Merchant_ID</td>
    <td class="tg-btxf">6</td>
    <td class="tg-btxf">Six-digit identifier issued by Kount.</td>
    <td class="tg-btxf">999999</td>
  </tr>
  <tr>
    <td class="tg-0pky">COMPANY_SERVER_URL</td>
    <td class="tg-0pky">N/A</td>
    <td class="tg-0pky">HTTPS URL path to the company’s servers provided in boarding documentation from Kount.</td>
    <td class="tg-0pky">https://risk.test.kount.net</td>
  </tr>
  <tr>
    <td class="tg-btxf">LOGGER</td>
    <td class="tg-btxf">N/A</td>
    <td class="tg-btxf">Specifies which logger to use: SIMPLE or NOP.</td>
    <td class="tg-btxf">SIMPLE</td>
  </tr>
  <tr>
    <td class="tg-0pky">SIMPLE_LOG_LEVEL</td>
    <td class="tg-0pky">N/A</td>
    <td class="tg-0pky">If SIMPLE logging is enabled, this lists logging levels in order of decreasing severity: FATAL, ERROR, WARN, INFO,DEBUG</td>
    <td class="tg-0pky">WARN</td>
  </tr>
  <tr>
    <td class="tg-btxf">SIMPLE_LOG_FILE</td>
    <td class="tg-btxf">N/A</td>
    <td class="tg-btxf">Name of the log file for SIMPLE logging</td>
    <td class="tg-btxf">company-sdk-ris.log</td>
  </tr>
  <tr>
    <td class="tg-0pky">SIMPLE_LOG_PATH</td>
    <td class="tg-0pky">N/A</td>
    <td class="tg-0pky">Path to where log file will be written. (Must be a valid path)</td>
    <td class="tg-0pky">/some/path/to/log</td>
  </tr>
  <tr>
    <td class="tg-btxf">APIKEY</td>
    <td class="tg-btxf">Varies</td>
    <td class="tg-btxf">API Key value copied from clipboard - originating from API Key page within Agent Web Console</td>
    <td class="tg-btxf">Alpha/Numeric hashed value provided by Kount</td>
  </tr>
  <tr>
    <td class="tg-0pky">Client Certificate (deprecated field for legacy certificates)</td>
    <td class="tg-0pky">N/A</td>
    <td class="tg-0pky">Depending on the SDK environment certain client certificate information will be required.</td>
    <td class="tg-0pky">company-ris- certificate.p12</td>
  </tr>
</table>
