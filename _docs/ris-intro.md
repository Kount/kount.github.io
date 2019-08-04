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
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#fff;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#f0f0f0;}
.tg .tg-wgsn{font-family:Arial, Helvetica, sans-serif !important;;border-color:inherit;text-align:left;vertical-align:top}
.tg .tg-v1a8{font-weight:bold;font-family:"Arial Black", Gadget, sans-serif !important;;background-color:#193d68;color:#ffffff;border-color:inherit;text-align:center;vertical-align:top}
.tg .tg-8wuw{background-color:#f9f9f9;font-family:Arial, Helvetica, sans-serif !important;;border-color:inherit;text-align:left;vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-v1a8">Data</th>
    <th class="tg-v1a8">Size</th>
    <th class="tg-v1a8">Description</th>
    <th class="tg-v1a8">Example</th>
  </tr>
  <tr>
    <td class="tg-8wuw">Merchant_ID</td>
    <td class="tg-8wuw">6</td>
    <td class="tg-8wuw">Six-digit identifier issued by Kount.</td>
    <td class="tg-8wuw">999999</td>
  </tr>
  <tr>
    <td class="tg-wgsn">COMPANY_SERVER_URL</td>
    <td class="tg-wgsn">N/A</td>
    <td class="tg-wgsn">HTTPS URL path to the company's servers provided in boarding documentation from Kount.</td>
    <td class="tg-wgsn"></td>
  </tr>
  <tr>
    <td class="tg-8wuw"></td>
    <td class="tg-8wuw"></td>
    <td class="tg-8wuw"></td>
    <td class="tg-8wuw"></td>
  </tr>
</table>
