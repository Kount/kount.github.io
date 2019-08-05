---
title: RIS API Keys 
tags:
---

To preserve the security of RIS data, merchants must authenticate to Kount using an API Key when submitting RIS requests. API Keys are created within the Agent Web Console. Additional coding examples can be found in the SDK Guide.

API Keys are used to track and control permissions to Kount APIs and RIS. Rather than creating separate certificates for APIs and RIS, a single API Key can be used to manage both.

{% include alert.html style="success" text="NOTE: For Kount Central customers, an API Key can manage APIs, RIS, and Kount Central permissions." %}

To open the API Key’s page, click Admin tab, choose API Keys. By default, no API Keys exist when the API Keys page is opened for the first time. To create a key, click the Create API Key button at the lower right of the table.

The Create API Key dialog box appears.

<ul class="uk-list uk-list-divider">
    <li>1.	Key Name: Give the new key a name.</li>
    <li>2.	Key Permissions: Select RIS, API, or both.</li>
    <li>3.	Create API Key: Click this button to create the key.</li>
</ul>

{% include alert.html style="success" text="NOTE: If the merchant is a Kount Central customer, a third check box for Kount Central will be present under Key Permissions and available to be selected." %}

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;border-color:#ccc;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#fff;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#f0f0f0;}
.tg .tg-9qtj{background-color:#193d68;color:#ffffff;text-align:center;vertical-align:top}
.tg .tg-buh4{background-color:#f9f9f9;text-align:left;vertical-align:top}
.tg .tg-0lax{text-align:left;vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-9qtj">﻿Field</th>
    <th class="tg-9qtj">Description</th>
  </tr>
  <tr>
    <td class="tg-buh4">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Name</td>
    <td class="tg-buh4">The name of the newly created key appears here.</td>
  </tr>
  <tr>
    <td class="tg-0lax">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Permissions</td>
    <td class="tg-0lax">The permissions given to the key during creation appear here.</td>
  </tr>
  <tr>
    <td class="tg-buh4">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Key</td>
    <td class="tg-buh4">The key value appears here.</td>
  </tr>
  <tr>
    <td class="tg-0lax">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Created</td>
    <td class="tg-0lax">The date and time the key was created appears here.</td>
  </tr>
  <tr>
    <td class="tg-buh4">&nbsp;&nbsp;&nbsp;&nbsp;Revoke (Gear)</td>
    <td class="tg-buh4">Click the ”gears” and then click Revoke to revoke the key.</td>
  </tr>
  <tr>
    <td class="tg-0lax">&nbsp;&nbsp;&nbsp;&nbsp;Create API Key (button)</td>
    <td class="tg-0lax">Click this button to create a new key. You can create as many keys as you want.&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</td>
  </tr>
  <tr>
    <td class="tg-buh4">&nbsp;&nbsp;&nbsp;&nbsp;Success Message</td>
    <td class="tg-buh4">"Like any other success message click on this green box to close it."</td>
  </tr>
</table>

Once you have created the API Key in the Agent Web Console, send the custom header request to Kount. The value of the header is the API Key generated in the Agent Web Console. Below are examples:

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;border-color:#ccc;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#fff;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#f0f0f0;}
.tg .tg-9qtj{background-color:#193d68;color:#ffffff;text-align:center;vertical-align:top}
.tg .tg-buh4{background-color:#f9f9f9;text-align:left;vertical-align:top}
.tg .tg-0lax{text-align:left;vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-9qtj">﻿Setting</th>
    <th class="tg-9qtj">Example</th>
  </tr>
  <tr>
    <td class="tg-buh4">   &nbsp;&nbsp;PHP settings.initial</td>
    <td class="tg-buh4">$ch = curl_init(); curl_setopt($ch, CURLOPT_HTTPHEADER, array("X-Kount-Api-Key: {$this-&gt;apiKey}"));</td>
  </tr>
  <tr>
    <td class="tg-0lax">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.NET App.config</td>
    <td class="tg-0lax">HttpWebRequest webReq = (HttpWebRequest)WebRequest.Create(this.url); webReq.Headers["X-Kount-Api-Key"] = this.apiKey;</td>
  </tr>
  <tr>
    <td class="tg-buh4">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Java</td>
    <td class="tg-buh4">URL url = new URL(this.risServerUrl); HttpsURLConnection urlConn = (HttpsURLConnection) url.openConnection(); urlConn.setRequestProperty("X-Kount-Api-Key", getApiKeyData());&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</td>
  </tr>
</table>
