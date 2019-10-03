---
title: RIS Error Codes
tags: [error codes] 
---

An important use of the RIS response is the ability to verify if the
decision-making process was successful and view any warnings or errors
that were made during the RIS post from the merchant. All warnings will
be displayed in the response and if errors do occur the RIS response
will be returned with a `MODE = E`.

Here's a list of all used RIS warning and error codes.

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg .tg-baqh{text-align:center;vertical-align:top}
.tg .tg-5197{font-weight:bold;font-size:15px;background-color:#193d68;color:#ffffff;text-align:center;vertical-align:top}
.tg .tg-pax9{font-weight:bold;font-size:15px;background-color:#193d68;color:#ffffff;text-align:left;vertical-align:top}
.tg .tg-0lax{text-align:left;vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-5197">﻿Response Code</th>
    <th class="tg-5197">Warning/Error Label</th>
    <th class="tg-pax9">Response Code Description</th>
  </tr>
  <tr>
    <td class="tg-baqh">201</td>
    <td class="tg-baqh">MISSING_VERS</td>
    <td class="tg-0lax">Missing version of Kount, this is built into SDK but must be supplied by merchant if not using the SDK</td>
  </tr>
  <tr>
    <td class="tg-baqh">202</td>
    <td class="tg-baqh">MISSING_MODE</td>
    <td class="tg-0lax">The mode type for post is missing. Refer to the RIS Modes page for more information. </td>
  </tr>
  <tr>
    <td class="tg-baqh">203</td>
    <td class="tg-baqh">MISSING_MERC</td>
    <td class="tg-0lax">The six digit Merchant ID was not sent</td>
  </tr>
  <tr>
    <td class="tg-baqh">204</td>
    <td class="tg-baqh">MISSING_SESS</td>
    <td class="tg-0lax">The unique session ID was not sent</td>
  </tr>
  <tr>
    <td class="tg-baqh">205</td>
    <td class="tg-baqh">MISSING_TRAN</td>
    <td class="tg-0lax">Transaction ID number</td>
  </tr>
  <tr>
    <td class="tg-baqh">211</td>
    <td class="tg-baqh">MISSING_CURR</td>
    <td class="tg-0lax">The currency was missing in the RIS submission</td>
  </tr>
  <tr>
    <td class="tg-baqh">212</td>
    <td class="tg-baqh">MISSING_TOTL</td>
    <td class="tg-0lax">The total amount was missing</td>
  </tr>
  <tr>
    <td class="tg-baqh">221</td>
    <td class="tg-baqh">MISSING_EMAL</td>
    <td class="tg-0lax">The email address was missing</td>
  </tr>
  <tr>
    <td class="tg-baqh">222</td>
    <td class="tg-baqh">MISSING_ANID</td>
    <td class="tg-0lax">For MODE = P RIS inquiries the caller ID is missing</td>
  </tr>
  <tr>
    <td class="tg-baqh">223</td>
    <td class="tg-baqh">MISSING_SITE</td>
    <td class="tg-0lax">The website identifier that was created in the Agent Web Console (DEFAULT is the default website ID) is missing</td>
  </tr>
  <tr>
    <td class="tg-baqh">231</td>
    <td class="tg-baqh">MISSING_PTYP</td>
    <td class="tg-0lax">The payment type is missing. Refer to the RIS Payment Types</td>
  </tr>
  <tr>
    <td class="tg-baqh">232</td>
    <td class="tg-baqh">MISSING_CARD</td>
    <td class="tg-0lax">The credit card information is missing</td>
  </tr>
  <tr>
    <td class="tg-baqh">233</td>
    <td class="tg-baqh">MISSING_MICR</td>
    <td class="tg-0lax">Missing Magnetic Ink Character Recognition string</td>
  </tr>
  <tr>
    <td class="tg-baqh">234</td>
    <td class="tg-baqh">MISSING_PYPL</td>
    <td class="tg-0lax">The PayPal Payer ID is missing</td>
  </tr>
  <tr>
    <td class="tg-baqh">235</td>
    <td class="tg-baqh">MISSING_PTOK</td>
    <td class="tg-0lax">The payment token is missing.</td>
  </tr>
  <tr>
    <td class="tg-baqh">241</td>
    <td class="tg-baqh">MISSING_IPAD</td>
    <td class="tg-0lax">The IP address is missing</td>
  </tr>
  <tr>
    <td class="tg-baqh">251</td>
    <td class="tg-baqh">MISSING_MACK</td>
    <td class="tg-0lax">The merchant acknowledgement is missing</td>
  </tr>
  <tr>
    <td class="tg-baqh">261</td>
    <td class="tg-baqh">MISSING_POST</td>
    <td class="tg-0lax">The RIS query submitted to Kount contained no data</td>
  </tr>
  <tr>
    <td class="tg-baqh">271</td>
    <td class="tg-baqh">MISSING_PROD_TYPE</td>
    <td class="tg-0lax">The shopping cart data array attribute is missing.</td>
  </tr>
  <tr>
    <td class="tg-baqh">272</td>
    <td class="tg-baqh">MISSING_PROD_ITEM</td>
    <td class="tg-0lax">The shopping cart data array attribute is missing.</td>
  </tr>
  <tr>
    <td class="tg-baqh">273</td>
    <td class="tg-baqh">MISSING_PROD_DESC</td>
    <td class="tg-0lax">The shopping cart data array attribute is missing.</td>
  </tr>
  <tr>
    <td class="tg-baqh">274</td>
    <td class="tg-baqh">MISSING_PROD_QUANT</td>
    <td class="tg-0lax">The shopping cart data array attribute is missing.</td>
  </tr>
  <tr>
    <td class="tg-baqh">275</td>
    <td class="tg-baqh">MISSING_PROD_PRICE</td>
    <td class="tg-0lax">The shopping cart data array attribute is missing.</td>
  </tr>
  <tr>
    <td class="tg-baqh">301</td>
    <td class="tg-baqh">BAD_VERS</td>
    <td class="tg-0lax">The version of Kount supplied by merchant does not fit the four integer parameter</td>
  </tr>
  <tr>
    <td class="tg-baqh">302</td>
    <td class="tg-baqh">BAD_MODE</td>
    <td class="tg-0lax">The mode type is invalid. Refer to the RIS Inquiry Service Modes: inquiry</td>
  </tr>
  <tr>
    <td class="tg-baqh">303</td>
    <td class="tg-baqh">BAD_MERC</td>
    <td class="tg-0lax">The six digit Merchant ID is malformed or wrong</td>
  </tr>
  <tr>
    <td class="tg-baqh">304</td>
    <td class="tg-baqh">BAD_SESS</td>
    <td class="tg-0lax">The unique session ID is invalid. Refer to the Data Collector</td>
  </tr>
  <tr>
    <td class="tg-baqh">305</td>
    <td class="tg-baqh">BAD_TRAN</td>
    <td class="tg-0lax">Transaction ID number is malformed</td>
  </tr>
  <tr>
    <td class="tg-baqh">311</td>
    <td class="tg-baqh">BAD_CURR</td>
    <td class="tg-0lax">The currency was wrong in the RIS submission</td>
  </tr>
  <tr>
    <td class="tg-baqh">312</td>
    <td class="tg-baqh">BAD_TOTL</td>
    <td class="tg-0lax">The total amount is wrong. TOTL is the whole number amount charged to customer</td>
  </tr>
  <tr>
    <td class="tg-baqh">321</td>
    <td class="tg-baqh">BAD_EMAL</td>
    <td class="tg-0lax">The email address does not meet required format or is greater than 64 characters in length</td>
  </tr>
  <tr>
    <td class="tg-baqh">322</td>
    <td class="tg-baqh">BAD_ANID</td>
    <td class="tg-0lax">For MODE = P RIS inquiries the caller ID is malformed</td>
  </tr>
  <tr>
    <td class="tg-baqh">323</td>
    <td class="tg-baqh">BAD_SITE</td>
    <td class="tg-0lax">The website identifier that was created in the Agent Web Console (DEFAULT is the default w website ID) does not match what was created in the AWC.</td>
  </tr>
  <tr>
    <td class="tg-baqh">324</td>
    <td class="tg-baqh">BAD_FRMT</td>
    <td class="tg-0lax">The specified format is wrong. Format options are key value pairs, XML, JSON, YAML</td>
  </tr>
  <tr>
    <td class="tg-baqh">331</td>
    <td class="tg-baqh">BAD_PTYP</td>
    <td class="tg-0lax">The payment type is wrong. Refer to the RIS Payment Types</td>
  </tr>
  <tr>
    <td class="tg-baqh">332</td>
    <td class="tg-baqh">BAD_CARD</td>
    <td class="tg-0lax">The credit card information is malformed or wrong, test cards do not work in the production environment</td>
  </tr>
  <tr>
    <td class="tg-baqh">333</td>
    <td class="tg-baqh">BAD_MICR</td>
    <td class="tg-0lax">Malformed or improper Magnetic Ink Character Recognition string.</td>
  </tr>
  <tr>
    <td class="tg-baqh">334</td>
    <td class="tg-baqh">BAD_PYPL</td>
    <td class="tg-0lax">The PayPal Payer ID is malformed or corrupt.</td>
  </tr>
  <tr>
    <td class="tg-baqh">335</td>
    <td class="tg-baqh">BAD_GOOG</td>
    <td class="tg-0lax">Malformed or improper Google Checkout Account ID string.</td>
  </tr>
  <tr>
    <td class="tg-baqh">336</td>
    <td class="tg-baqh">BAD_BLML</td>
    <td class="tg-0lax">Malformed or improper Bill Me Later account number.</td>
  </tr>
  <tr>
    <td class="tg-baqh">337</td>
    <td class="tg-baqh">BAD_PENC</td>
    <td class="tg-0lax">The encryption method specified is wrong.</td>
  </tr>
  <tr>
    <td class="tg-baqh">338</td>
    <td class="tg-baqh">BAD_GDMP</td>
    <td class="tg-0lax">The GreenDot payment token is not a valid payment token</td>
  </tr>
  <tr>
    <td class="tg-baqh">339</td>
    <td class="tg-baqh">BAD_HASH</td>
    <td class="tg-0lax">When payment type equals CARD, PTYP = CARD and payment encryption type equals KHASH, `PENC = KHASH the value must be 20 characters in length.</td>
  </tr>
  <tr>
    <td class="tg-baqh">340</td>
    <td class="tg-baqh">BAD_MASK</td>
    <td class="tg-0lax">Invalid or excessive characters in the PTOK field</td>
  </tr>
  <tr>
    <td class="tg-baqh">341</td>
    <td class="tg-baqh">BAD_IPAD</td>
    <td class="tg-0lax">The IP address does not match specifications</td>
  </tr>
  <tr>
    <td class="tg-baqh">342</td>
    <td class="tg-baqh">BAD_GIFT</td>
    <td class="tg-0lax">The Gift Card payment token is invalid due to invalid characters, null, or exceeding character length</td>
  </tr>
  <tr>
    <td class="tg-baqh">351</td>
    <td class="tg-baqh">BAD_MACK</td>
    <td class="tg-0lax">The merchant acknowledgement must be Y or N</td>
  </tr>
  <tr>
    <td class="tg-baqh">362</td>
    <td class="tg-baqh">BAD_CART</td>
    <td class="tg-0lax">There is a discrepancy in the shopping cart key count and the number of items actually being sent in the cart</td>
  </tr>
  <tr>
    <td class="tg-baqh">371</td>
    <td class="tg-baqh">BAD_PROD_TYPE</td>
    <td class="tg-0lax">The shopping cart data array attribute is missing.</td>
  </tr>
  <tr>
    <td class="tg-baqh">372</td>
    <td class="tg-baqh">BAD_PROD_ITEM</td>
    <td class="tg-0lax">The shopping cart data array attribute is corrupt or missing.</td>
  </tr>
  <tr>
    <td class="tg-baqh">373</td>
    <td class="tg-baqh">BAD_PROD_DESC</td>
    <td class="tg-0lax">The shopping cart data array attribute is corrupt or missing.</td>
  </tr>
  <tr>
    <td class="tg-baqh">374</td>
    <td class="tg-baqh">BAD_PROD_QUANT</td>
    <td class="tg-0lax">The shopping cart data array attribute is corrupt or missing.</td>
  </tr>
  <tr>
    <td class="tg-baqh">375</td>
    <td class="tg-baqh">BAD_PROD_PRICE</td>
    <td class="tg-0lax">The shopping cart data array attribute is corrupt or missing.</td>
  </tr>
  <tr>
    <td class="tg-baqh">399</td>
    <td class="tg-baqh">BAD_OPTN</td>
    <td class="tg-0lax">A UDF has been mistyped or does not exist in the Agent Web Console</td>
  </tr>
  <tr>
    <td class="tg-baqh">401</td>
    <td class="tg-baqh">EXTRA_DATA</td>
    <td class="tg-0lax">RIS keys submitted by merchant were not part of SDK</td>
  </tr>
  <tr>
    <td class="tg-baqh">404</td>
    <td class="tg-baqh">UNNECESSARY_PTOK</td>
    <td class="tg-0lax">When PTYP equals NONE and a PTOK is submitted</td>
  </tr>
  <tr>
    <td class="tg-baqh">413</td>
    <td class="tg-baqh">REQUEST_ENTITY_TOO_ LARGE</td>
    <td class="tg-0lax">The RIS Post to Kount exceeded the 4K limit.</td>
  </tr>
  <tr>
    <td class="tg-baqh">501</td>
    <td class="tg-baqh">UNAUTH_REQ</td>
    <td class="tg-0lax">Error regarding certificate - Using test certificate in prod</td>
  </tr>
  <tr>
    <td class="tg-baqh">502</td>
    <td class="tg-baqh">UNAUTH_MERC</td>
    <td class="tg-0lax">Invalid Merchant ID has been entered</td>
  </tr>
  <tr>
    <td class="tg-baqh">601</td>
    <td class="tg-baqh">SYS_ERR</td>
    <td class="tg-0lax">Unspecified system error - Contact Merchant Services</td>
  </tr>
  <tr>
    <td class="tg-baqh">602</td>
    <td class="tg-baqh">SYS_NOPROCESS</td>
    <td class="tg-0lax">Kount will not process particular transaction</td>
  </tr>
  <tr>
    <td class="tg-baqh">701</td>
    <td class="tg-baqh">NO_HDR</td>
    <td class="tg-0lax">No header found with merchantId = [XXXXX], session_id = [htot2kk5khpamo45f777q455], trans=[122347] This error occurs when a RIS request goes to the database and there is no data available in the reply. The Update post had an invalid transaction ID#. Check all required fields for update post and confirm they are being passed correctly.</td>
  </tr>
</table>

-  **Missing**: When this designation appears, the customer has failed
   to complete a required field.
-  **Bad**: When this designation appears, some data was sent but failed
   to meet specifications. This could also be explained as malformed
   data or bad code that did not meet specifications, such as
   `AVS = W` instead of `AVS = M`.
