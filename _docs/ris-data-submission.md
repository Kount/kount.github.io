---
title: RIS Data Submission
tags: [featured]
---

When submitting data to RIS, it is recommended to send as much data as possible. As part of the RIS post there are required fields and if not populated an error will be returned in the RIS response. Please refer to the SDK documentation with details on how to submit the data for both optional and required fields.

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg .tg-fr0y{background-color:#656565;color:#ffffff;border-color:inherit;text-align:left;vertical-align:top}
.tg .tg-loqm{font-weight:bold;background-color:#656565;color:#ffffff;border-color:#656565;text-align:left;vertical-align:top}
.tg .tg-lzqt{font-weight:bold;background-color:#656565;color:#ffffff;border-color:inherit;text-align:center;vertical-align:top}
.tg .tg-c3ow{border-color:inherit;text-align:center;vertical-align:top}
.tg .tg-nakj{font-weight:bold;background-color:#656565;color:#ffffff;border-color:inherit;text-align:left;vertical-align:top}
.tg .tg-0pky{border-color:inherit;text-align:left;vertical-align:top}
.tg .tg-3ya8{font-weight:bold;background-color:#656565;color:#ffffff;border-color:#656565;text-align:center;vertical-align:top}
</style>
<table class="tg" style="undefined;table-layout: fixed; width: 702px">
<colgroup>
<col style="width: 110px">
<col style="width: 420px">
<col style="width: 109px">
<col style="width: 63px">
</colgroup>
  <tr>
    <th class="tg-lzqt">﻿Attribute</th>
    <th class="tg-nakj">Description</th>
    <th class="tg-nakj">Data Type &amp; Size</th>
    <th class="tg-nakj">Mode</th>
  </tr>
  <tr>
    <td class="tg-c3ow">VERS</td>
    <td class="tg-0pky">Specifies version of Kount Risk Inquiry Service built into SDK; must be supplied by merchant if not using the SDK.</td>
    <td class="tg-0pky">4 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P,X,U</td>
  </tr>
  <tr>
    <td class="tg-c3ow">MERC</td>
    <td class="tg-0pky">Merchant ID assigned to the merchant by Kount.</td>
    <td class="tg-0pky">6 characters numeric</td>
    <td class="tg-0pky">Q,P,X,U</td>
  </tr>
  <tr>
    <td class="tg-c3ow">MODE</td>
    <td class="tg-0pky">Specifies RIS mode.<br><br>Q: RIS call that does not originate from a call center environment.<br><br>P: RIS call that originates from a call center environment.<br><br>X: Call made after an initial MODE=Q or P request and/or any MODE=U updates have been made. Updates to certain fields can be made and the transaction will be re-evaluated and return an updated RIS response to the merchant.<br><br>U: Update call to Kount, does not cause a reevaluation of the transaction but will update what is displayed in the Agent Web Console (AWC). This update call does not count towards the number of RIS transactions purchased. Only certain fields can be updated with MODE=U calls. The PTYP field can only be updated if the initial post to Kount was PTYP=NONE.</td>
    <td class="tg-0pky">1 character alpha-numeric</td>
    <td class="tg-0pky">Q,P,X,U</td>
  </tr>
  <tr>
    <td class="tg-c3ow">SESS</td>
    <td class="tg-0pky">Unique Session ID. Must be unique over a 30-day span.</td>
    <td class="tg-0pky">32 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P,X,U</td>
  </tr>
  <tr>
    <td class="tg-c3ow">SITE</td>
    <td class="tg-0pky">Website identifier of where order originated.</td>
    <td class="tg-0pky">8 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">IPAD</td>
    <td class="tg-0pky">Dotted Decimal IPv4 address that the merchant sees coming from the customer. If MODE=P or the Phone to Web exclusion is used, the IPAD field should be hard coded to be 10.0.0.1. Other than MODE=P or Phone to Web, the IPAD field should never be an anonymous IP address (i.e. 10.X.X.X or 192.168.X.X).</td>
    <td class="tg-0pky">16 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">ORDR</td>
    <td class="tg-0pky">Merchant’s Order Number</td>
    <td class="tg-0pky">32 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P,U</td>
  </tr>
  <tr>
    <td class="tg-c3ow">MACK</td>
    <td class="tg-0pky">Merchants acknowledgement to ship/process the order.<br>(Must be Hard coded to "Y"" on initial RIS)<br>Y or N </td>
    <td class="tg-0pky">1 character (Y,N)</td>
    <td class="tg-0pky">QPU</td>
  </tr>
  <tr>
    <td class="tg-c3ow">ANID</td>
    <td class="tg-0pky">Automatic Number Identification (Caller ID) submitted with order. If the ANI cannot be determined, merchant must pass 0123456789 as the ANID. This field is only valid for MODE=P RIS submissions.</td>
    <td class="tg-0pky">32 characters alpha-numeric</td>
    <td class="tg-0pky">P</td>
  </tr>
  <tr>
    <td class="tg-lzqt">Payment Information</td>
    <td class="tg-nakj"></td>
    <td class="tg-nakj"></td>
    <td class="tg-nakj"></td>
  </tr>
  <tr>
    <td class="tg-c3ow">PTOK</td>
    <td class="tg-0pky">Payment token submitted by merchant for order (credit card, payer ID, routing/transit, MICR, and account number).<br><br>When using KHASH the BIN is extracted from the PTOK value, Last4 may be passed independently - it is lost during KHASH.<br><br>If PTYP is set to None then the PTOK value should be left empty (NULL).POST-AUTH ONLY - If the credit card information is not available and a tokenized value is returned from the payment processor set PTYP=TOKEN and send the token returned from processor in the PTOK field.</td>
    <td class="tg-0pky">32 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P,U</td>
  </tr>
  <tr>
    <td class="tg-c3ow">LAST4</td>
    <td class="tg-0pky">Last 4 numbers of Credit Card Value</td>
    <td class="tg-0pky">4 characters numeric</td>
    <td class="tg-0pky">Q,P,U</td>
  </tr>
  <tr>
    <td class="tg-c3ow">PTYP</td>
    <td class="tg-0pky">Payment Type submitted by merchant:<br>APAY - Apple Pay<br>CARD - Credit Card   <br>**PENC is a required field when PTYP=CARD<br>PYPL - PayPal<br>CHEK - Check<br>NONE - None<br>TOKEN - Token provided from payment processor<br>GDMP - Green Dot Money Pack<br>GOOG - Google Checkout<br>BLML - Bill Me Later<br>GIFT - Gift Card<br>BPAY - BPAY<br>NETELLER - Neteller<br>GIROPAY - GiroPay<br>ELV - ELV<br>MERCADE_PAGO - Mercade Pago<br>SEPA - Single Euro Payments Area<br>INTERAC - Interac<br>CARTE_BLEUE - Carte Bleue<br>POLI - POLi<br>SKRILL - Skrill/Moneybookers <br>SOFORT - Sofort</td>
    <td class="tg-0pky">4 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P,U</td>
  </tr>
  <tr>
    <td class="tg-c3ow">PENC</td>
    <td class="tg-0pky">RIS Parameter for Payment Encoding&nbsp;&nbsp;(2 acceptable values)PENC is only required when PTYP=CARD.</td>
    <td class="tg-0pky">KHASH or MASK</td>
    <td class="tg-0pky">Q,P,X</td>
  </tr>
  <tr>
    <td class="tg-c3ow">TOTL</td>
    <td class="tg-0pky">Total amount in currency submitted in lowest currency factor. e.g. USD = pennies($1.00 = 100). TOTL must be a natural number including 0.</td>
    <td class="tg-0pky">15 characters numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">AUTH</td>
    <td class="tg-0pky">Authorization Status returned to merchant from processor.A: AuthorizedD: DeclinedIn orders where AUTH=A will aggregate towards order velocity of the persona while orders where AUTH=D will decrement the velocity of the persona.</td>
    <td class="tg-0pky">1 character alpha-numeric</td>
    <td class="tg-0pky">Q,P,U</td>
  </tr>
  <tr>
    <td class="tg-c3ow">CURR</td>
    <td class="tg-0pky">Country of currency submitted on order.&nbsp;&nbsp;If event or transaction is not a payment transaction, then hard code any ISO 3 digit approved currency code</td>
    <td class="tg-0pky">3 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">AVST</td>
    <td class="tg-0pky">Address Verification System Street verification response returned to merchant from processor.M: MatchN: No MatchX: Unsupported or Unavailable</td>
    <td class="tg-0pky">1 character alpha-numeric</td>
    <td class="tg-0pky">Q,P,U</td>
  </tr>
  <tr>
    <td class="tg-c3ow">AVSZ</td>
    <td class="tg-0pky">Address Verification System Zip Code verification response returned to merchant from processor.M: MatchN: No MatchX: Unsupported or Unavailable</td>
    <td class="tg-0pky">1 character alpha-numeric</td>
    <td class="tg-0pky">Q,P,U</td>
  </tr>
  <tr>
    <td class="tg-c3ow">CVVR</td>
    <td class="tg-0pky">Card Verification Value response returned to merchant from processor. Acceptable values are ’M’ for match, ’N’ for no-match, or ’X’ unsupported or unavailable.</td>
    <td class="tg-0pky">1 character</td>
    <td class="tg-0pky">Q,P,U</td>
  </tr>
  <tr>
    <td class="tg-3ya8">Billing Information</td>
    <td class="tg-loqm"></td>
    <td class="tg-loqm"></td>
    <td class="tg-loqm"></td>
  </tr>
  <tr>
    <td class="tg-c3ow">EMAL</td>
    <td class="tg-0pky">This is the email address submitted by the customer. If a call center is accepting orders on behalf of customers and the customer does not provide an email address OR the customer does not have an email address, noemail@kount.com must be submitted.</td>
    <td class="tg-0pky">64 characters alpha-numeric</td>
    <td class="tg-0pky">Q</td>
  </tr>
  <tr>
    <td class="tg-c3ow">NAME</td>
    <td class="tg-0pky">Name submitted with the order</td>
    <td class="tg-0pky">64 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">B2A1</td>
    <td class="tg-0pky">Billing street address - Line 1</td>
    <td class="tg-0pky">256 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">B2A2</td>
    <td class="tg-0pky">Billing street address - Line 2</td>
    <td class="tg-0pky">256 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">B2CI</td>
    <td class="tg-0pky">Billing address - City</td>
    <td class="tg-0pky">256 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">B2ST</td>
    <td class="tg-0pky">Billing address - State/Province</td>
    <td class="tg-0pky">256 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">B2PC</td>
    <td class="tg-0pky">Billing address - Postal Code</td>
    <td class="tg-0pky">20 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">B2CC</td>
    <td class="tg-0pky">Billing address - Country</td>
    <td class="tg-0pky">2 characters alpha</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">B2PN</td>
    <td class="tg-0pky">Bill-to Phone Number</td>
    <td class="tg-0pky">32 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">BPREMISE</td>
    <td class="tg-0pky">Bill-to premise address for UK (Required for 192.com)</td>
    <td class="tg-0pky">256 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">BSTREET</td>
    <td class="tg-0pky">Bill-to street address for UK (Required for 192.com)</td>
    <td class="tg-0pky">256 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-lzqt">Shipping Information</td>
    <td class="tg-nakj"></td>
    <td class="tg-nakj"></td>
    <td class="tg-nakj"></td>
  </tr>
  <tr>
    <td class="tg-c3ow">S2A1</td>
    <td class="tg-0pky">Shipping street address - Line 1</td>
    <td class="tg-0pky">256 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">S2A2</td>
    <td class="tg-0pky">Shipping street address - Line 2</td>
    <td class="tg-0pky">256 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">S2CI</td>
    <td class="tg-0pky">Shipping address - City</td>
    <td class="tg-0pky">2 characters alpha</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">S2CC</td>
    <td class="tg-0pky">Shipping address - Country</td>
    <td class="tg-0pky">256 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">S2EM</td>
    <td class="tg-0pky">Shipping address - Email address of recipient</td>
    <td class="tg-0pky">64 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">S2NM</td>
    <td class="tg-0pky">Shipping address - Name of recipient</td>
    <td class="tg-0pky">64 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">S2PC</td>
    <td class="tg-0pky">Shipping address - Postal Code</td>
    <td class="tg-0pky">20 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">S2PN</td>
    <td class="tg-0pky">Ship-to Phone Number</td>
    <td class="tg-0pky">32 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">S2ST</td>
    <td class="tg-0pky">Shipping address - State/Province</td>
    <td class="tg-0pky">256 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">SHTP</td>
    <td class="tg-0pky">Shipping type. The following nomenclature is expectedfor shipping types to be passed to Kount.SHTP:Same Day = SDNext Day = NDSecond Day = 2DStandard = ST</td>
    <td class="tg-0pky">2 characters alpha</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">SPREMISE</td>
    <td class="tg-0pky">Ship-to premise address for UK (Required for 192.com)</td>
    <td class="tg-0pky">256 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">SSTREET</td>
    <td class="tg-0pky">Ship-to street address for UK (Required for 192.com)</td>
    <td class="tg-0pky">256 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-lzqt">Product Details</td>
    <td class="tg-fr0y"></td>
    <td class="tg-fr0y"></td>
    <td class="tg-fr0y"></td>
  </tr>
  <tr>
    <td class="tg-c3ow">PROD_DESC[ ]</td>
    <td class="tg-0pky">Shopping cart data array attribute for a specific description of the item being purchased.</td>
    <td class="tg-0pky">0-255 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">PROD_ITEM[ ]</td>
    <td class="tg-0pky">Shopping cart data array attribute typically the SKU for an item; this value should be free from any markup or Unicode values. This value should be passed as plain text.</td>
    <td class="tg-0pky">1-255 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">PROD_PRICE[ ]</td>
    <td class="tg-0pky">Shopping cart data array attribute for the price of the single item. Must be a natural number including 0.</td>
    <td class="tg-0pky">Integer (Long)</td>
    <td class="tg-0pky">Q, P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">PROD_QUANT[ ]</td>
    <td class="tg-0pky">Shopping cart data array attribute signifying the quantity of the item being purchased.</td>
    <td class="tg-0pky">Integer (Long)</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">PROD_TYPE[ ]</td>
    <td class="tg-0pky">Shopping cart data array attribute high level or generalized description of the item added to the shopping cart; this value should be free from any markup or Unicode values. This value should be passed as plain text.</td>
    <td class="tg-0pky">1-255 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-lzqt">Miscellaneous Information</td>
    <td class="tg-fr0y"></td>
    <td class="tg-fr0y"></td>
    <td class="tg-fr0y"></td>
  </tr>
  <tr>
    <td class="tg-c3ow">CASH</td>
    <td class="tg-0pky">Total fenceable value of goods sold.</td>
    <td class="tg-0pky">15 characters numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">EPOC</td>
    <td class="tg-0pky">This is timestamp associated with the creation of a user ID and is expressed as a number such as 1422377956. The timestamp value represents the number of seconds elapsed since midnight 01/01/1970. Reference: http://www.epochconverter.com/.</td>
    <td class="tg-0pky">10 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">DOB</td>
    <td class="tg-0pky">Date of Birth</td>
    <td class="tg-0pky">YYYY-MM-DD</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">GENDER</td>
    <td class="tg-0pky">M or F</td>
    <td class="tg-0pky">1 character</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">UNIQ</td>
    <td class="tg-0pky">Merchant assigned account number for consumer</td>
    <td class="tg-0pky">32 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">UAGT</td>
    <td class="tg-0pky">Customer User-Agent HTTP header</td>
    <td class="tg-0pky">1024 characeters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">FRMT</td>
    <td class="tg-0pky">Specifies the format of the RIS response if not using SDK,XML, JSON, YAML</td>
    <td class="tg-0pky">4 characters alpha-numeric</td>
    <td class="tg-0pky">Q,P</td>
  </tr>
  <tr>
    <td class="tg-c3ow">RFCB</td>
    <td class="tg-0pky">Refund/Chargeback status.R: RefundC: Chargeback</td>
    <td class="tg-0pky">1 character alpha-numeric</td>
    <td class="tg-0pky">U</td>
  </tr>
</table>
