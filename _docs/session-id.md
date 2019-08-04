---
title: Session ID Discussion
subtitle: The Session ID is the unique identifier for the collection event and is specific to the user’s request. You will use the Session ID for subsequent calls to the Inquiry Service.
tags: [features]
author: Jarrett
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
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#fff;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#f0f0f0;}
.tg .tg-buh4{background-color:#f9f9f9;text-align:left;vertical-align:top}
.tg .tg-i5ij{background-color:#193d68;color:#ffffff;text-align:left;vertical-align:top}
.tg .tg-0lax{text-align:left;vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-i5ij">﻿VAR</th>
    <th class="tg-i5ij">Description</th>
    <th class="tg-i5ij">Sample</th>
  </tr>
  <tr>
    <td class="tg-buh4">m</td>
    <td class="tg-buh4">Six digit Merchant ID number issued by Kount.</td>
    <td class="tg-buh4">m=123456</td>
  </tr>
  <tr>
    <td class="tg-0lax">s</td>
    <td class="tg-0lax">32 character session ID, see session ID discussion for more information.</td>
    <td class="tg-0lax">s=abcdefg12345abababab123456789012</td>
  </tr>
  <tr>
    <td class="tg-buh4">DATA_COLLECTOR_URL</td>
    <td class="tg-buh4">The URLs for the Data Collector are Environment specific. There is a URL for Test and a URL for Production. The URL must be obtained from Client Success.Please contact your Client SuccessManager or support@kount.com</td>
    <td class="tg-buh4"></td>
  </tr>
</table>
