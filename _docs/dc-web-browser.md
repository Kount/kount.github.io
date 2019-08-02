---
title: Web Clients or Browser
subtitle:
tags:
author: Jarrett
---

The Data Collector runs on a client’s browser and collects a variety of information that helps uniquely
identify the device. Add the <script> tag to the web page where you want to trigger the Data Collection.
The variables are found in the above table. Below is sample code.

{% include alert.html style="primary" text="High Level Integration Steps" %}

<ul class="uk-list uk-list-divider">
    <li>1. Update the Content Security Policy to the header of the page.</li>
    <li>2. Add the load event to the class kaxsdc in the BODY (this may be attached to a different html
element).</li>
    <li>3. Add the Script tag with the correct Data Collection URL, Merchant ID and Session value.</li>
    <li>4. Set the ka.ClientSDK to autorun when kaxsdc class loads.</li>
</ul>
