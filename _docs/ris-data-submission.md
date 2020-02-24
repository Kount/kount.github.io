---
title: RIS Data Submission
tags: [featured]
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
<table style="undefined;table-layout: fixed; width: 1127px">
<colgroup>
<col style="width: 188px">
<col style="width: 116px">
<col style="width: 550px">
<col style="width: 212px">
<col style="width: 61px">
</colgroup>
  <tr>
    <th>﻿Attribute</th>
    <th>Importance</th>
    <th>Description</th>
    <th>Data Type &amp; Size</th>
    <th>Mode</th>
  </tr>
  <tr>
    <td>VERS</td>
    <td>1</td>
    <td>Specifies version of Kount Risk Inquiry Service built into SDK; must be supplied by merchant if not using the SDK.</td>
    <td>4 characters alpha-numeric</td>
    <td>Q,P,X,U</td>
  </tr>
  <tr>
    <td>MERC</td>
    <td>1</td>
    <td>Merchant ID assigned to the merchant by Kount.</td>
    <td>6 characters numeric</td>
    <td>Q,P,X,U</td>
  </tr>
  <tr>
    <td>MODE</td>
    <td>1</td>
    <td>Specifies RIS mode.<br><br>Q: RIS call that does not originate from a call center environment.<br><br>P: RIS call that originates from a call center environment.<br><br>X: Call made after an initial MODE=Q or P request and/or any MODE=U updates have been made. Updates to certain fields can be made and the transaction will be re-evaluated and return an updated RIS response to the merchant.<br><br>U: Update call to Kount, does not cause a reevaluation of the transaction but will update what is displayed in the Agent Web Console (AWC). This update call does not count towards the number of RIS transactions purchased. Only certain fields can be updated with MODE=U calls. The PTYP field can only be updated if the initial post to Kount was PTYP=NONE.</td>
    <td>1 character alpha-numeric</td>
    <td>Q,P,X,U</td>
  </tr>
  <tr>
    <td>SESS</td>
    <td>1</td>
    <td>Unique Session ID. Must be unique over a 30-day span.</td>
    <td>32 characters alpha-numeric</td>
    <td>Q,P,X,U</td>
  </tr>
  <tr>
    <td>SITE</td>
    <td>1</td>
    <td>Website identifier of where order originated.</td>
    <td>8 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>IPAD</td>
    <td>1</td>
    <td>Dotted Decimal IPv4 address that the merchant sees coming from the customer. If MODE=P or the Phone to Web exclusion is used, the IPAD field should be hard coded to be 10.0.0.1. Other than MODE=P or Phone to Web, the IPAD field should never be an anonymous IP address (i.e. 10.X.X.X or 192.168.X.X).</td>
    <td>16 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>ORDR</td>
    <td>2</td>
    <td>Merchant’s Order Number</td>
    <td>32 characters alpha-numeric</td>
    <td>Q,P,U</td>
  </tr>
  <tr>
    <td>MACK</td>
    <td>1</td>
    <td>Merchants acknowledgement to ship/process the order.<br>(Must be Hard coded to "Y"" on initial RIS)<br>Y or N </td>
    <td>1 character (Y,N)</td>
    <td>QPU</td>
  </tr>
  <tr>
    <td>ANID</td>
    <td>1</td>
    <td>Automatic Number Identification (Caller ID) submitted with order. If the ANI cannot be determined, merchant must pass 0123456789 as the ANID. This field is only valid for MODE=P RIS submissions.</td>
    <td>32 characters alpha-numeric</td>
    <td>P</td>
  </tr>
  <tr>
    <td>Payment Information</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>PTOK</td>
    <td>1</td>
    <td>Payment token submitted by merchant for order (credit card, payer ID, routing/transit, MICR, and account number).<br><br>When using KHASH the BIN is extracted from the PTOK value, Last4 may be passed independently - it is lost during KHASH.<br><br>If PTYP is set to None then the PTOK value should be left empty (NULL).POST-AUTH ONLY - If the credit card information is not available and a tokenized value is returned from the payment processor set PTYP=TOKEN and send the token returned from processor in the PTOK field.</td>
    <td>32 characters alpha-numeric</td>
    <td>Q,P,U</td>
  </tr>
  <tr>
    <td>LAST4</td>
    <td>3</td>
    <td>Last 4 numbers of Credit Card Value</td>
    <td>4 characters numeric</td>
    <td>Q,P,U</td>
  </tr>
  <tr>
    <td>PTYP</td>
    <td>1</td>
    <td>Payment Type submitted by merchant:<br>APAY - Apple Pay<br>CARD - Credit Card   <br>**PENC is a required field when PTYP=CARD<br>PYPL - PayPal<br>CHEK - Check<br>NONE - None<br>TOKEN - Token provided from payment processor<br>GDMP - Green Dot Money Pack<br>GOOG - Google Checkout<br>BLML - Bill Me Later<br>GIFT - Gift Card<br>BPAY - BPAY<br>NETELLER - Neteller<br>GIROPAY - GiroPay<br>ELV - ELV<br>MERCADE_PAGO - Mercade Pago<br>SEPA - Single Euro Payments Area<br>INTERAC - Interac<br>CARTE_BLEUE - Carte Bleue<br>POLI - POLi<br>SKRILL - Skrill/Moneybookers <br>SOFORT - Sofort</td>
    <td>4 characters alpha-numeric</td>
    <td>Q,P,U</td>
  </tr>
  <tr>
    <td>PENC</td>
    <td>1</td>
    <td>RIS Parameter for Payment Encoding&nbsp;&nbsp;(2 acceptable values)PENC is only required when PTYP=CARD.</td>
    <td>KHASH or MASK</td>
    <td>Q,P,X</td>
  </tr>
  <tr>
    <td>TOTL</td>
    <td>1</td>
    <td>Total amount in currency submitted in lowest currency factor. e.g. USD = pennies($1.00 = 100). TOTL must be a natural number including 0.</td>
    <td>15 characters numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>AUTH</td>
    <td>1</td>
    <td>Authorization Status returned to merchant from processor.A: AuthorizedD: DeclinedIn orders where AUTH=A will aggregate towards order velocity of the persona while orders where AUTH=D will decrement the velocity of the persona.</td>
    <td>1 character alpha-numeric</td>
    <td>Q,P,U</td>
  </tr>
  <tr>
    <td>CURR</td>
    <td>1</td>
    <td>Country of currency submitted on order.&nbsp;&nbsp;If event or transaction is not a payment transaction, then hard code any ISO 3 digit approved currency code</td>
    <td>3 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>AVST</td>
    <td>1</td>
    <td>Address Verification System Street verification response returned to merchant from processor.M: MatchN: No MatchX: Unsupported or Unavailable</td>
    <td>1 character alpha-numeric</td>
    <td>Q,P,U</td>
  </tr>
  <tr>
    <td>AVSZ</td>
    <td>1</td>
    <td>Address Verification System Zip Code verification response returned to merchant from processor.M: MatchN: No MatchX: Unsupported or Unavailable</td>
    <td>1 character alpha-numeric</td>
    <td>Q,P,U</td>
  </tr>
  <tr>
    <td>CVVR</td>
    <td>1</td>
    <td>Card Verification Value response returned to merchant from processor. Acceptable values are ’M’ for match, ’N’ for no-match, or ’X’ unsupported or unavailable.</td>
    <td>1 character</td>
    <td>Q,P,U</td>
  </tr>
  <tr>
    <td>Billing Information</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>EMAL</td>
    <td>1</td>
    <td>This is the email address submitted by the customer. If a call center is accepting orders on behalf of customers and the customer does not provide an email address OR the customer does not have an email address, noemail@kount.com must be submitted.</td>
    <td>64 characters alpha-numeric</td>
    <td>Q</td>
  </tr>
  <tr>
    <td>NAME</td>
    <td>1</td>
    <td>Name submitted with the order</td>
    <td>64 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>B2A1</td>
    <td>1</td>
    <td>Billing street address - Line 1</td>
    <td>256 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>B2A2</td>
    <td>1</td>
    <td>Billing street address - Line 2</td>
    <td>256 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>B2CI</td>
    <td>1</td>
    <td>Billing address - City</td>
    <td>256 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>B2ST</td>
    <td>1</td>
    <td>Billing address - State/Province</td>
    <td>256 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>B2PC</td>
    <td>1</td>
    <td>Billing address - Postal Code</td>
    <td>20 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>B2CC</td>
    <td>1</td>
    <td>Billing address - Country</td>
    <td>2 characters alpha</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>B2PN</td>
    <td>1</td>
    <td>Bill-to Phone Number</td>
    <td>32 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>BPREMISE</td>
    <td>2</td>
    <td>Bill-to premise address for UK (Required for 192.com)</td>
    <td>256 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>BSTREET</td>
    <td>2</td>
    <td>Bill-to street address for UK (Required for 192.com)</td>
    <td>256 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>Shipping Information</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>S2A1</td>
    <td>1</td>
    <td>Shipping street address - Line 1</td>
    <td>256 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>S2A2</td>
    <td>1</td>
    <td>Shipping street address - Line 2</td>
    <td>256 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>S2CI</td>
    <td>1</td>
    <td>Shipping address - City</td>
    <td>2 characters alpha</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>S2CC</td>
    <td>1</td>
    <td>Shipping address - Country</td>
    <td>256 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>S2EM</td>
    <td>1</td>
    <td>Shipping address - Email address of recipient</td>
    <td>64 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>S2NM</td>
    <td>1</td>
    <td>Shipping address - Name of recipient</td>
    <td>64 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>S2PC</td>
    <td>1</td>
    <td>Shipping address - Postal Code</td>
    <td>20 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>S2PN</td>
    <td>1</td>
    <td>Ship-to Phone Number</td>
    <td>32 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>S2ST</td>
    <td>1</td>
    <td>Shipping address - State/Province</td>
    <td>256 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>SHTP</td>
    <td>1</td>
    <td>Shipping type. The following nomenclature is expectedfor shipping types to be passed to Kount.SHTP:Same Day = SDNext Day = NDSecond Day = 2DStandard = ST</td>
    <td>2 characters alpha</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>SPREMISE</td>
    <td>3</td>
    <td>Ship-to premise address for UK (Required for 192.com)</td>
    <td>256 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>SSTREET</td>
    <td>3</td>
    <td>Ship-to street address for UK (Required for 192.com)</td>
    <td>256 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>Product Details</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>PROD_DESC[ ]</td>
    <td>1</td>
    <td>Shopping cart data array attribute for a specific description of the item being purchased.</td>
    <td>0-255 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>PROD_ITEM[ ]</td>
    <td>1</td>
    <td>Shopping cart data array attribute typically the SKU for an item; this value should be free from any markup or Unicode values. This value should be passed as plain text.</td>
    <td>1-255 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>PROD_PRICE[ ]</td>
    <td>1</td>
    <td>Shopping cart data array attribute for the price of the single item. Must be a natural number including 0.</td>
    <td>Integer (Long)</td>
    <td>Q, P</td>
  </tr>
  <tr>
    <td>PROD_QUANT[ ]</td>
    <td>1</td>
    <td>Shopping cart data array attribute signifying the quantity of the item being purchased.</td>
    <td>Integer (Long)</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>PROD_TYPE[ ]</td>
    <td>1</td>
    <td>Shopping cart data array attribute high level or generalized description of the item added to the shopping cart; this value should be free from any markup or Unicode values. This value should be passed as plain text.</td>
    <td>1-255 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>Miscellaneous Information</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>CASH</td>
    <td>2</td>
    <td>Total fenceable value of goods sold.</td>
    <td>15 characters numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>EPOC</td>
    <td>1</td>
    <td>This is timestamp associated with the creation of a user ID and is expressed as a number such as 1422377956. The timestamp value represents the number of seconds elapsed since midnight 01/01/1970. Reference: http://www.epochconverter.com/.</td>
    <td>10 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>DOB</td>
    <td>3</td>
    <td>Date of Birth</td>
    <td>YYYY-MM-DD</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>GENDER</td>
    <td>3</td>
    <td>M or F</td>
    <td>1 character</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>UNIQ</td>
    <td>1</td>
    <td>Merchant assigned account number for consumer</td>
    <td>32 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>UAGT</td>
    <td>1</td>
    <td>Customer User-Agent HTTP header</td>
    <td>1024 characeters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>FRMT</td>
    <td>3</td>
    <td>Specifies the format of the RIS response if not using SDK,XML, JSON, YAML</td>
    <td>4 characters alpha-numeric</td>
    <td>Q,P</td>
  </tr>
  <tr>
    <td>RFCB</td>
    <td>1</td>
    <td>Refund/Chargeback status.R: RefundC: Chargeback</td>
    <td>1 character alpha-numeric</td>
    <td>U</td>
  </tr>
</table>
