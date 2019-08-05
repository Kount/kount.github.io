---
title: RIS Data Submission
tags:
---

When submitting data to RIS, it is recommended to send as much data as possible. As part of the RIS post there are required fields and if not populated an error will be returned in the RIS response. Please refer to the SDK documentation with details on how to submit the data for both optional and required fields.

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;border-color:#ccc;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#fff;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#f0f0f0;}
.tg .tg-oq6y{background-color:#193d68;color:#ffffff;border-color:#000000;text-align:center;vertical-align:top}
.tg .tg-aa13{background-color:#f9f9f9;border-color:#000000;text-align:center;vertical-align:top}
.tg .tg-kcxh{background-color:#008699;color:#ffffff;border-color:#000000;text-align:left;vertical-align:middle}
.tg .tg-wp8o{border-color:#000000;text-align:center;vertical-align:top}
.tg .tg-ksh9{background-color:#193d68;color:#ffffff;border-color:#000000;text-align:center;vertical-align:top}
.tg .tg-i817{background-color:#f9f9f9;border-color:#000000;text-align:left;vertical-align:top}
.tg .tg-73oq{border-color:#000000;text-align:left;vertical-align:top}
.tg .tg-ret9{background-color:#008699;color:#ffffff;border-color:#000000;text-align:center;vertical-align:middle}
</style>
<table class="tg">
  <tr>
    <th class="tg-oq6y">﻿RIS Required Inquiry Key</th>
    <th class="tg-oq6y">Description</th>
    <th class="tg-oq6y">Max Field Length</th>
    <th class="tg-oq6y">Source</th>
    <th class="tg-oq6y">Required</th>
  </tr>
  <tr>
    <td class="tg-aa13">ANID</td>
    <td class="tg-i817">Automatic Number Identification (ANI) submitted with order. If the ANI cannot be determined, merchant must pass 0123456789 as the ANID. This field is only valid for MODE=P RIS submissions.</td>
    <td class="tg-aa13">32</td>
    <td class="tg-aa13">Merchant</td>
    <td class="tg-i817">MODE=P</td>
  </tr>
  <tr>
    <td class="tg-wp8o">AUTH</td>
    <td class="tg-73oq">Authorization Status returned to merchant from processor. Acceptable values for the AUTH field are ’A’ for Authorized or ’D’ for Decline. In orders where AUTH=A will aggregate towards order velocity of the persona while orders where AUTH=D will decrement the velocity of the persona.</td>
    <td class="tg-wp8o">1</td>
    <td class="tg-wp8o">Merchant</td>
    <td class="tg-73oq">MODE=Q MODE=P</td>
  </tr>
  <tr>
    <td class="tg-aa13">CURR</td>
    <td class="tg-i817">Country of currency submitted on order</td>
    <td class="tg-aa13">3</td>
    <td class="tg-aa13">Merchant</td>
    <td class="tg-i817">MODE=Q MODE=P</td>
  </tr>
  <tr>
    <td class="tg-wp8o">EMAL</td>
    <td class="tg-73oq">Email address submitted by customer. If a call center is accepting orders on behalf of customers and the customer does not provide an email address, noemail@Kount.com must be submitted. Kount currently supports 2 bit character sets. Unicode character sets are not supported at this time.</td>
    <td class="tg-wp8o">64</td>
    <td class="tg-wp8o">Merchant</td>
    <td class="tg-73oq">MODE=Q</td>
  </tr>
  <tr>
    <td class="tg-aa13">IPAD</td>
    <td class="tg-i817">Dotted Decimal IPv4 address that the merchant sees coming from the customer. If MODE=P or the Phone to Web exclusion is used, the IPAD field should be hard coded to be 10.0.0.1. Other than MODE=P or Phone to Web, the IPAD field should never be an anonymous IP address (i.e. 10.X.X.X or 192.168.X.X). IPv6 Addresses are not currently supported. Please use the IPv4 dual stack equivalent or pass 10.0.0.1 in the IPAD field if an IPv4 address is not available.</td>
    <td class="tg-aa13">16</td>
    <td class="tg-aa13">Merchant</td>
    <td class="tg-i817">MODE=Q MODE=P</td>
  </tr>
  <tr>
    <td class="tg-wp8o">MACK</td>
    <td class="tg-73oq">Merchants acknowledgement to ship/process the order. The MACK field must be set as ’Y’ if persona data is to be collected to strengthen the score.</td>
    <td class="tg-wp8o">1</td>
    <td class="tg-wp8o">Merchant</td>
    <td class="tg-73oq">MODE=Q MODE=P</td>
  </tr>
  <tr>
    <td class="tg-aa13">MERC</td>
    <td class="tg-i817">Merchant ID assigned to the merchant by Kount.</td>
    <td class="tg-aa13">6</td>
    <td class="tg-aa13">Merchant</td>
    <td class="tg-i817">MODE=Q MODE=P MODE=X MODE=U</td>
  </tr>
  <tr>
    <td class="tg-wp8o">MODE</td>
    <td class="tg-73oq">Specifies what mode type the RIS post is: -MODE - Q-MODE - P-MODE -U-MODE - X</td>
    <td class="tg-wp8o">1</td>
    <td class="tg-wp8o">Merchant</td>
    <td class="tg-73oq">MODE=Q MODE=P MODE=X MODE=U</td>
  </tr>
  <tr>
    <td class="tg-aa13">PROD_DESC</td>
    <td class="tg-i817">Shopping cart data array attribute for specific description of the item being purchased.-NOTE: Product description should not contain any markup or uniocode values. Non-alpha numeric characters will increment the character count exponetially depending on the special character used. RIS Post limits: There is a 40,960 character/byte limit that makes up an entire RIS post. Should the RIS post exceed the 40,960 byte limit, an HTTP standard error will be returned, typically an error code: 413 - Request Entity Too Large</td>
    <td class="tg-aa13">256</td>
    <td class="tg-aa13">Merchant</td>
    <td class="tg-i817">MODE=Q MODE=P</td>
  </tr>
  <tr>
    <td class="tg-wp8o">PROD_ITEM</td>
    <td class="tg-73oq">Shopping cart data array attribute typically the SKU for an item; this value should be free from any markup or Unicode values. This value should be passed as plain text.</td>
    <td class="tg-wp8o">256</td>
    <td class="tg-wp8o">Merchant</td>
    <td class="tg-73oq">MODE=Q MODE=P</td>
  </tr>
  <tr>
    <td class="tg-aa13">PROD_PRICE</td>
    <td class="tg-i817">Shopping cart data array attribute for the price of the single item. Must be a natural number including 0.</td>
    <td class="tg-aa13">no max</td>
    <td class="tg-aa13">Merchant</td>
    <td class="tg-i817">MODE=Q MODE=P</td>
  </tr>
  <tr>
    <td class="tg-wp8o">PROD_QUANT</td>
    <td class="tg-73oq">Shopping cart data array attribute signifying the quantity of the item being purchased</td>
    <td class="tg-wp8o">no max</td>
    <td class="tg-wp8o">Merchant</td>
    <td class="tg-73oq">MODE=Q MODE=P</td>
  </tr>
  <tr>
    <td class="tg-aa13">PROD_TYPE</td>
    <td class="tg-i817">Shopping cart data array attribute high level or generalized description of the item added to the shopping cart; this value should be free from any markup or Unicode values. This value should be passed as plain text.</td>
    <td class="tg-aa13">256</td>
    <td class="tg-aa13">Merchant</td>
    <td class="tg-i817">MODE=Q MODE=P</td>
  </tr>
  <tr>
    <td class="tg-wp8o">PTOK</td>
    <td class="tg-73oq">Payment token submitted by merchant for order (credit card, payer ID, routing/transit, MICR, and account number). When using KHASH the BIN is extracted from the PTOK value, Last4 may be passed independently - it is lost during KHASH.</td>
    <td class="tg-wp8o">32</td>
    <td class="tg-wp8o">Merchant</td>
    <td class="tg-73oq">MODE=Q MODE=P</td>
  </tr>
  <tr>
    <td class="tg-aa13">PTYP</td>
    <td class="tg-i817">Payment Type submitted by merchant - See below PTYP VALUES</td>
    <td class="tg-aa13">varies</td>
    <td class="tg-aa13">Merchant</td>
    <td class="tg-i817">MODE=Q MODE=P</td>
  </tr>
  <tr>
    <td class="tg-ret9">PTYP VALUE</td>
    <td class="tg-kcxh" colspan="4">Description</td>
  </tr>
  <tr>
    <td class="tg-aa13">APAY</td>
    <td class="tg-i817">Apple Pay</td>
    <td class="tg-aa13" colspan="3" rowspan="20"></td>
  </tr>
  <tr>
    <td class="tg-wp8o">CARD</td>
    <td class="tg-73oq">Credit Card</td>
  </tr>
  <tr>
    <td class="tg-aa13">PYPL</td>
    <td class="tg-i817">PayPal</td>
  </tr>
  <tr>
    <td class="tg-wp8o">CHEK</td>
    <td class="tg-73oq">Check</td>
  </tr>
  <tr>
    <td class="tg-aa13">NONE</td>
    <td class="tg-i817">None</td>
  </tr>
  <tr>
    <td class="tg-wp8o">GDMP</td>
    <td class="tg-73oq">Green Dot Money Pack</td>
  </tr>
  <tr>
    <td class="tg-aa13">GOOG</td>
    <td class="tg-i817">Google Checkout</td>
  </tr>
  <tr>
    <td class="tg-wp8o">BLML</td>
    <td class="tg-73oq">Bill Me Later</td>
  </tr>
  <tr>
    <td class="tg-aa13">GIFT</td>
    <td class="tg-i817">Gift Card</td>
  </tr>
  <tr>
    <td class="tg-wp8o">BPAY</td>
    <td class="tg-73oq">Bpay</td>
  </tr>
  <tr>
    <td class="tg-aa13">NETELLER</td>
    <td class="tg-i817">Neteller</td>
  </tr>
  <tr>
    <td class="tg-wp8o">GIROPAY</td>
    <td class="tg-73oq">GiroPay</td>
  </tr>
  <tr>
    <td class="tg-aa13">ELV</td>
    <td class="tg-i817">ELV</td>
  </tr>
  <tr>
    <td class="tg-wp8o">MERCADE_PAGO</td>
    <td class="tg-73oq">Mercade Pago</td>
  </tr>
  <tr>
    <td class="tg-aa13">SEPA </td>
    <td class="tg-i817">Single Euro Payments Area</td>
  </tr>
  <tr>
    <td class="tg-wp8o">INTERAC</td>
    <td class="tg-73oq">Interac</td>
  </tr>
  <tr>
    <td class="tg-aa13">POLI</td>
    <td class="tg-i817">POLI</td>
  </tr>
  <tr>
    <td class="tg-wp8o">SKRILL</td>
    <td class="tg-73oq">Srkill/Moneybookers</td>
  </tr>
  <tr>
    <td class="tg-aa13">SOFORT</td>
    <td class="tg-i817">Sofort</td>
  </tr>
  <tr>
    <td class="tg-wp8o">TOKEN</td>
    <td class="tg-73oq">Token</td>
  </tr>
  <tr>
    <td class="tg-ksh9">RIS Required Inquiry Key</td>
    <td class="tg-ksh9">Description</td>
    <td class="tg-ksh9">Max Field Length</td>
    <td class="tg-ksh9">Source</td>
    <td class="tg-ksh9">Required</td>
  </tr>
  <tr>
    <td class="tg-wp8o">SESS</td>
    <td class="tg-73oq">Unique Session ID</td>
    <td class="tg-wp8o">32</td>
    <td class="tg-wp8o">Merchant</td>
    <td class="tg-73oq">MODE=Q MODE=P MODE=X MODE=U</td>
  </tr>
  <tr>
    <td class="tg-aa13">SITE</td>
    <td class="tg-i817">Website identifier of where order originated. Value must exist inside of the Agent Web Console prior to post.</td>
    <td class="tg-aa13">8</td>
    <td class="tg-aa13">Merchant</td>
    <td class="tg-i817">MODE=Q MODE=P</td>
  </tr>
  <tr>
    <td class="tg-wp8o">TOTL</td>
    <td class="tg-73oq">Total amount in currency submitted in lowest currency factor. e.g. USD= pennies ($1.00 = 100). TOTL must be a natural number including 0.</td>
    <td class="tg-wp8o">15</td>
    <td class="tg-wp8o">Merchant</td>
    <td class="tg-73oq">MODE=Q MODE=P</td>
  </tr>
  <tr>
    <td class="tg-aa13">TRAN</td>
    <td class="tg-i817">Transaction ID required for update calls to Kount. MODE=U and MODE=X</td>
    <td class="tg-aa13"></td>
    <td class="tg-aa13">Kount</td>
    <td class="tg-i817">MODE=U MODE=X</td>
  </tr>
  <tr>
    <td class="tg-wp8o">VERS</td>
    <td class="tg-73oq">Specifies the version of Kount built into SDK, must be supplied by merchant if not using the SDK</td>
    <td class="tg-wp8o">4</td>
    <td class="tg-wp8o">Kount-Merchant</td>
    <td class="tg-73oq">MODE=Q MODE=P MODE=X MODE=U</td>
  </tr>
</table>
