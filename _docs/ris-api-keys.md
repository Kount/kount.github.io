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

