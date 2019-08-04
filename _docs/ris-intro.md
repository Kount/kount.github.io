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
.tg .tg-0y7w{font-weight:bold;font-family:"Courier New", Courier, monospace !important;;border-color:inherit;text-align:center;vertical-align:top}
.tg .tg-9gth{font-family:"Courier New", Courier, monospace !important;;border-color:inherit;text-align:left;vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-0y7w">Data</th>
    <th class="tg-0y7w">Size</th>
    <th class="tg-0y7w">Description</th>
    <th class="tg-0y7w">Example</th>
  </tr>
  <tr>
    <td class="tg-9gth">Merchant_ID</td>
    <td class="tg-9gth">6</td>
    <td class="tg-9gth">Six-digit identifier issued<br>by Kount.</td>
    <td class="tg-9gth">999999</td>
  </tr>
  <tr>
    <td class="tg-9gth"></td>
    <td class="tg-9gth"></td>
    <td class="tg-9gth"></td>
    <td class="tg-9gth"></td>
  </tr>
  <tr>
    <td class="tg-9gth"></td>
    <td class="tg-9gth"></td>
    <td class="tg-9gth"></td>
    <td class="tg-9gth"></td>
  </tr>
</table>
