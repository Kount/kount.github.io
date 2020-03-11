---
title: User Defined Fields
subtitle: Kount provides a way for merchants to include additional information related to their business that may not be a standard field in Kount by creating user defined fields.
tags: [UDF]
---

**User Defined Fields (UDF)** are created in the Agent Web Console by browsing to the Fraud Control tab and clicking on User Defined Fields. 

{% include image.html img="ezgif.com-optimize.gif" alt="User Defined Field Demo" %}

Once you have defined the UDF in the Agent Web Console you will be able to pass this data into Kount via an array called UDF as key-value pairs where the label is the key and the data passed in is the value. The maximum number of UDFs that can be created is 500, and response time for evaluating transactions will degrade as more UDFs are added. There are four data types available for user defined fields.



## User Defined Fields - Data Types

##### Number 
* This UDF type is not eligible for VIP List options or for Velocity tracking; however, it is available for use in the Kount Rules Engine.

##### Alpha-Numeric
* This UDF type is eligible for VIP List Management, as well as for tracking Persona Velocities within the Kount Rules Engine. Separate VIP Lists for the values being passed in these UDFs may be created. Additionally, Persona Velocity for a specific value contained within the UDF may be tracked.

##### Date 
* This UDF type is not eligible for VIP List options or for Velocity tracking; however, it is available for use in the Kount Rules Engine.

##### Amount 
* This UDF type is not eligible for VIP List options or for Velocity tracking; however, it is available for use in the Kount Rules Engine.

{% include alert.html style="success" text="NOTE: UDF labels can be up to 28 characters in length and cannot begin with a number."%}

<style type="text/css"> .tg {border-collapse:collapse;border-spacing:0;border-color:#ccc;} .tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#fff;} .tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#f0f0f0;} .tg .tg-9qtj{background-color:#193d68;color:#ffffff;text-align:center;vertical-align:top} .tg .tg-buh4{background-color:#f9f9f9;text-align:left;vertical-align:top} .tg .tg-0lax{text-align:left;vertical-align:top} </style>
<table class="tg">
  <tr>
    <th class="tg-9qtj">﻿Attribute</th>
    <th class="tg-9qtj">Size</th>
    <th class="tg-9qtj">Description</th>
    <th class="tg-9qtj">Example</th>
  </tr>
  <tr>
    <td class="tg-buh4">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UDF[NUMERIC_LABEL]=value</td>
    <td class="tg-buh4">1-255</td>
    <td class="tg-buh4">Whole numbers and decimal points.</td>
    <td class="tg-buh4">UDF[FREQUENCY]=107.9&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</td>
  </tr>
  <tr>
    <td class="tg-0lax">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UDF[ALPHA_NUMERIC_LABEL]=value</td>
    <td class="tg-0lax">1-255</td>
    <td class="tg-0lax">Letters, numbers or both.</td>
    <td class="tg-0lax">UDF[COUPON]=BUY11</td>
  </tr>
  <tr>
    <td class="tg-buh4">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UDF[DATE_LABEL]=value</td>
    <td class="tg-buh4">1-19</td>
    <td class="tg-buh4">Formatted as YYYY-MM-DD or YYYY-MM-DD HH:MI:SS</td>
    <td class="tg-buh4">UDF[FIRST_CONTACT]</td>
  </tr>
  <tr>
    <td class="tg-0lax">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UDF[AMOUNT_LABEL]=value </td>
    <td class="tg-0lax">1-255</td>
    <td class="tg-0lax">Integers only, no decimal points, signs or symbols.</td>
    <td class="tg-0lax">UDF[BALANCE]=1100</td>
  </tr>
</table>
