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


<div class="uk-child-width-1-2@s uk-grid-match" uk-grid>
    <div>
        <div class="uk-card uk-card-default uk-card-body">
            <h3 class="uk-card-title">Mode Q</h3>
            <p>Initial queries directed from the merchant to Kount that do not originate from a call center
environment.</p>
        </div>
    </div>
    <div>
        <div class="uk-card uk-card-default uk-card-hover uk-card-body">
            <h3 class="uk-card-title">Mode P</h3>
            <p>Initial queries originating from a call center environment.</p>
        </div>
    </div>

<table class="uk-table uk-table-striped uk-table-hover uk-text-bold">
    <thead>
        <tr>
            <th>Data</th>
            <th>Size</th>
            <th>Description</th>
            <th>Example</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Merchant ID</td>
            <td>6</td>
            <td>Six-digit identifier issued by Kount.</td>
            <td>999999</td>
        </tr>
        <tr>
            <td>COMPANY_SERVER_URL</td>
            <td>N/A</td>
            <td>HTTPS URL path to the
company’s servers provided in boarding documentation from Kount.</td>
            <td>https://risk.test.kount.net</td>
        </tr>
        <tr>
            <td>Table Data</td>
            <td>Table Data</td>
            <td>Table Data</td>
            <td>Table Data</td>
        </tr>
        <tr>
            <td>999999</td>
            <td>Table Data</td>
            <td>Table Data</td>
            <td>Table Data</td>
        </tr>
    </tbody>
</table>

<div class="datatable-begin"></div>

Food    | Description                           | Category | Sample type
------- | ------------------------------------- | -------- | -----------
Apples  | A small, somewhat round ...           | Fruit    | Fuji
Bananas | A long and curved, often-yellow ...   | Fruit    | Snow
Kiwis   | A small, hairy-skinned sweet ...      | Fruit    | Golden
Oranges | A spherical, orange-colored sweet ... | Fruit    | Navel

<div class="datatable-end"></div>

<table>
<colgroup>
<col width="30%" />
<col width="70%" />
</colgroup>
<thead>
<tr class="header">
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">First column **fields**</td>
<td markdown="span">Some descriptive text. This is a markdown link to [Google](http://google.com). Or see [some link][mydoc_tags].</td>
</tr>
<tr>
<td markdown="span">Second column **fields**</td>
<td markdown="span">Some more descriptive text.
</td>
</tr>
</tbody>
</table>
