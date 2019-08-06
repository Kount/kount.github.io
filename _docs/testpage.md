---
title: Test New
tags:
---

<ul class="uk-tab uk-flex-center" uk-switcher>
    <li><a href="#">Mode Q</a></li>
    <li><a href="#">Mode P</a></li>
    <li><a href="#">Mode U</a></li>
    <li><a href="#">Mode X</a></li>
    <li><a href="#">Mode E</a></li>
</ul>

<ul class="uk-switcher uk-text-center uk-text-large uk-margin">
    <li>Test</li>
    <li>Hello again!</li>
    <li>Mode U<table style="border-collapse:collapse;border-spacing:0;border-color:#ccc" class="tg"><tr><th style="font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 20px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:inherit;color:#ffffff;background-color:#193d68;text-align:center;vertical-align:top">﻿VAR</th><th style="font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 20px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:inherit;color:#ffffff;background-color:#193d68;text-align:left;vertical-align:top">Description</th><th style="font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 20px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:inherit;color:#ffffff;background-color:#193d68;text-align:center;vertical-align:top">Sample</th></tr><tr><td style="font-family:Arial, sans-serif;font-size:14px;padding:10px 20px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:inherit;color:#333;background-color:#f9f9f9;text-align:center;vertical-align:top">m</td><td style="font-family:Arial, sans-serif;font-size:14px;padding:10px 20px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:inherit;color:#333;background-color:#f9f9f9;text-align:left;vertical-align:top">Six digit Merchant ID number issued by Kount.</td><td style="font-family:Arial, sans-serif;font-size:14px;padding:10px 20px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:inherit;color:#333;background-color:#f9f9f9;text-align:center;vertical-align:top">m=123456</td></tr><tr><td style="font-family:Arial, sans-serif;font-size:14px;padding:10px 20px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:inherit;color:#333;background-color:#fff;text-align:center;vertical-align:top">s</td><td style="font-family:Arial, sans-serif;font-size:14px;padding:10px 20px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:inherit;color:#333;background-color:#fff;text-align:left;vertical-align:top">32 character session ID, see session ID discussion for more information.</td><td style="font-family:Arial, sans-serif;font-size:14px;padding:10px 20px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:inherit;color:#333;background-color:#fff;text-align:center;vertical-align:top">s=abcdefg12345abababab123456789012&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</td></tr><tr><td style="font-family:Arial, sans-serif;font-size:14px;padding:10px 20px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:inherit;color:#333;background-color:#f9f9f9;text-align:center;vertical-align:top">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DATA_COLLECTOR_URL</td><td style="font-family:Arial, sans-serif;font-size:14px;padding:10px 20px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:inherit;color:#333;background-color:#f9f9f9;text-align:left;vertical-align:top">The URLs for the Data Collector are Environment specific. There is a URL for Test and a URL for Production. The URL must be obtained from Client Success.Please contact your Client SuccessManager or support@kount.com</td><td style="font-family:Arial, sans-serif;font-size:14px;padding:10px 20px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:inherit;color:#333;background-color:#f9f9f9;text-align:center;vertical-align:top"></td></tr></table></li>
     <li>Test</li>
     <li><table class="wdn_responsive_table flush-left"  id="t284208">
<caption></caption>
<tbody>
      <tr>
            <td colspan="1" id="t284208_row_0col_0">ANID</td>
            <td colspan="1" id="t284208_row_0col_1">Automatic Number Identification (ANI) submitted with order. If the ANI cannot be determined, merchant must pass 0123456789 as the ANID. This field is only valid for MODE=P RIS submissions.</td>
            <td colspan="1" id="t284208_row_0col_2">32</td>
            <td colspan="1" id="t284208_row_0col_3">Merchant</td>
            <td colspan="1" id="t284208_row_0col_4">MODE=P</td>
       </tr>
      <tr>
            <td colspan="1" id="t284208_row_1col_0">AUTH</td>
            <td colspan="1" id="t284208_row_1col_1">Authorization Status returned to merchant from processor. Acceptable values for the AUTH field are ’A’ for Authorized or ’D’ for Decline. In orders where AUTH=A will aggregate towards order velocity of the persona while orders where AUTH=D will decrement the velocity of the persona.</td>
            <td colspan="1" id="t284208_row_1col_2">1</td>
            <td colspan="1" id="t284208_row_1col_3">Merchant</td>
            <td colspan="1" id="t284208_row_1col_4">MODE=Q MODE=P</td>
       </tr>
      <tr>
            <td colspan="1" id="t284208_row_2col_0">CURR</td>
            <td colspan="1" id="t284208_row_2col_1">Country of currency submitted on order</td>
            <td colspan="1" id="t284208_row_2col_2">3</td>
            <td colspan="1" id="t284208_row_2col_3">Merchant</td>
            <td colspan="1" id="t284208_row_2col_4">MODE=Q MODE=P</td>
       </tr>
      <tr>
            <td colspan="1" id="t284208_row_3col_0">EMAL</td>
            <td colspan="1" id="t284208_row_3col_1">Email address submitted by customer. If a call center is accepting orders on behalf of customers and the customer does not provide an email address, noemail@Kount.com must be submitted. Kount currently supports 2 bit character sets. Unicode character sets are not supported at this time.</td>
            <td colspan="1" id="t284208_row_3col_2">64</td>
            <td colspan="1" id="t284208_row_3col_3">Merchant</td>
            <td colspan="1" id="t284208_row_3col_4">MODE=Q</td>
       </tr>
      <tr>
            <td colspan="1" id="t284208_row_4col_0">IPAD</td>
            <td colspan="1" id="t284208_row_4col_1">Dotted Decimal IPv4 address that the merchant sees coming from the customer. If MODE=P or the Phone to Web exclusion is used, the IPAD field should be hard coded to be 10.0.0.1. Other than MODE=P or Phone to Web, the IPAD field should never be an anonymous IP address (i.e. 10.X.X.X or 192.168.X.X). IPv6 Addresses are not currently supported. Please use the IPv4 dual stack equivalent or pass 10.0.0.1 in the IPAD field if an IPv4 address is not available.</td>
            <td colspan="1" id="t284208_row_4col_2">16</td>
            <td colspan="1" id="t284208_row_4col_3">Merchant</td>
            <td colspan="1" id="t284208_row_4col_4">MODE=Q MODE=P</td>
       </tr>
      <tr>
            <td colspan="1" id="t284208_row_5col_0">MACK</td>
            <td colspan="1" id="t284208_row_5col_1">Merchants acknowledgement to ship/process the order. The MACK field must be set as ’Y’ if persona data is to be collected to strengthen the score.</td>
            <td colspan="1" id="t284208_row_5col_2">1</td>
            <td colspan="1" id="t284208_row_5col_3">Merchant</td>
            <td colspan="1" id="t284208_row_5col_4">MODE=Q MODE=P</td>
       </tr>
      <tr>
            <td colspan="1" id="t284208_row_6col_0">MERC</td>
            <td colspan="1" id="t284208_row_6col_1">Merchant ID assigned to the merchant by Kount.</td>
            <td colspan="1" id="t284208_row_6col_2">6</td>
            <td colspan="1" id="t284208_row_6col_3">Merchant</td>
            <td colspan="1" id="t284208_row_6col_4">MODE=Q MODE=P MODE=X MODE=U</td>
       </tr>
      <tr>
            <td colspan="1" id="t284208_row_7col_0">MODE</td>
            <td colspan="1" id="t284208_row_7col_1">Specifies what mode type the RIS post is: -MODE - Q-MODE - P-MODE -U-MODE - X</td>
            <td colspan="1" id="t284208_row_7col_2">1</td>
            <td colspan="1" id="t284208_row_7col_3">Merchant</td>
            <td colspan="1" id="t284208_row_7col_4">MODE=Q MODE=P MODE=X MODE=U</td>
       </tr>
      <tr>
            <td colspan="1" id="t284208_row_8col_0">PROD_DESC</td>
            <td colspan="1" id="t284208_row_8col_1">Shopping cart data array attribute for specific description of the item being purchased.-NOTE: Product description should not contain any markup or uniocode values. Non-alpha numeric characters will increment the character count exponetially depending on the special character used. RIS Post limits: There is a 40,960 character/byte limit that makes up an entire RIS post. Should the RIS post exceed the 40,960 byte limit, an HTTP standard error will be returned, typically an error code: 413 - Request Entity Too Large</td>
            <td colspan="1" id="t284208_row_8col_2">256</td>
            <td colspan="1" id="t284208_row_8col_3">Merchant</td>
            <td colspan="1" id="t284208_row_8col_4">MODE=Q MODE=P</td>
       </tr>
</tbody>
</table></li>
</ul>


<div>
        <img src="kountbrandedheroimage.svg" width="50" height="50">
        <span class="uk-text-top">Lorem ipsum.</span>
    </div>
