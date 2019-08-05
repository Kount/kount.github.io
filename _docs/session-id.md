---
title: Session ID Discussion
subtitle: The Session ID is the unique identifier for the collection event and is specific to the user’s request. You will use the Session ID for subsequent calls to the Inquiry Service.
tags: [features]
author: 
---

## Session ID Details
* Data Collector should be run once for each user’s session within the web browser.
* Session IDs must be unique per request. They must be unique for a minimum of 30 days.
* Session ID values must be alpha-numeric values (0-9, a-z or A-Z). Dashes (-) and underscores (_)
are acceptable.
* Session ID values should be 32 characters in length. Session ID values of less than 32 characters
will be accepted, but it is strongly recommended to use a 32 character value. Note: 32
characters is the maximum number of characters, an error will be thrown if the Session ID
exceeds 32 characters.

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;border-color:#ccc;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 20px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#fff;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 20px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#f0f0f0;}
.tg .tg-9qtj{background-color:#193d68;color:#ffffff;text-align:center;vertical-align:top}
.tg .tg-baqh{text-align:center;vertical-align:top}
.tg .tg-buh4{background-color:#f9f9f9;text-align:left;vertical-align:top}
.tg .tg-i5ij{background-color:#193d68;color:#ffffff;text-align:left;vertical-align:top}
.tg .tg-dzk6{background-color:#f9f9f9;text-align:center;vertical-align:top}
.tg .tg-0lax{text-align:left;vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-9qtj">﻿VAR</th>
    <th class="tg-i5ij">Description</th>
    <th class="tg-9qtj">Sample</th>
  </tr>
  <tr>
    <td class="tg-dzk6">m</td>
    <td class="tg-buh4">Six digit Merchant ID number issued by Kount.</td>
    <td class="tg-dzk6">m=123456</td>
  </tr>
  <tr>
    <td class="tg-baqh">s</td>
    <td class="tg-0lax">32 character session ID, see session ID discussion for more information.</td>
    <td class="tg-baqh">s=abcdefg12345abababab123456789012</td>
  </tr>
  <tr>
    <td class="tg-dzk6">DATA_COLLECTOR_URL</td>
    <td class="tg-buh4">The URLs for the Data Collector are Environment specific. There is a URL for Test and a URL for Production. The URL must be obtained from Client Success.Please contact your Client SuccessManager or support@kount.com</td>
    <td class="tg-dzk6"></td>
  </tr>
</table>

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
    <td class="tg-btxf">Six-digit identifier issued by Kount.<br>-<br>-</td>
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
