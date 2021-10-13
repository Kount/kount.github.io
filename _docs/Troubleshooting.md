---
title: RIS Warning and Error Codes
tags: [error codes] 
---

### The information on this site has moved to [support.kount.com](support.kount.com). Please update any bookmarks and note that this site will be taken down November 30th. Using the information found on this site might cause unexpected results.

An important use of the RIS response is the ability to verify if the decision-making process was successful and view any warnings or errors that were made during the RIS post from the merchant. All warnings will be displayed in the response and if errors do occur the RIS response will be returned with a `MODE = E`.

Here's a list of all used RIS warning and error codes.

<style type="text/css"> .tg {border-collapse:collapse;border-spacing:0;} .tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;} .tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;} .tg .tg-3e2f{font-weight:bold;font-size:15px;font-family:Arial, Helvetica, sans-serif !important;;background-color:#193d68;color:#ffffff;border-color:inherit;text-align:center;vertical-align:top} .tg .tg-c3ow{border-color:inherit;text-align:center;vertical-align:top} </style>
<table class="tg" style="overflow-x:auto">
<col width="17%" />
<col width="25%" />
<col width="57%" />
<thead>
<tr class="header">
<th align="left">Response Code</th>
<th align="left">Warning/Error Label</th>
<th align="left">Response Code Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">201</td>
<td align="left"><code>MISSING_VERS</code></td>
<td align="left">Missing version of Kount, this is built into SDK but must be supplied by merchant if not using the SDK</td>
</tr>
<tr class="even">
<td align="left">202</td>
<td align="left"><code>MISSING_MODE</code></td>
<td align="left">
<p>The mode type for post is missing. Refer to the</p>
<a href="Request-types-and-Parameters.html">Request Types</a></td>
</tr>
<tr class="odd">
<td align="left">203</td>
<td align="left"><code>MISSING_MERC</code></td>
<td align="left">The six digit Merchant ID was not sent</td>
</tr>
<tr class="even">
<td align="left">204</td>
<td align="left"><code>MISSING_SESS</code></td>
<td align="left">The unique session ID was not sent</td>
</tr>
<tr class="odd">
<td align="left">205</td>
<td align="left"><code>MISSING_TRAN</code></td>
<td align="left">Transaction ID number</td>
</tr>
<tr class="even">
<td align="left">211</td>
<td align="left"><code>MISSING_CURR</code></td>
<td align="left">The currency was missing in the RIS submission</td>
</tr>
<tr class="odd">
<td align="left">212</td>
<td align="left"><code>MISSING_TOTL</code></td>
<td align="left">The total amount was missing</td>
</tr>
<tr class="even">
<td align="left">221</td>
<td align="left"><code>MISSING_EMAL</code></td>
<td align="left">The email address was missing</td>
</tr>
<tr class="odd">
<td align="left">222</td>
<td align="left"><code>MISSING_ANID</code></td>
<td align="left">For <code>MODE = P</code> RIS inquiries the caller ID is missing</td>
</tr>
<tr class="even">
<td align="left">223</td>
<td align="left"><code>MISSING_SITE</code></td>
<td align="left">The website identifier that was created in the Agent Web Console (<code>DEFAULT</code> is the default website ID) is missing</td>
</tr>
<tr class="odd">
<td align="left">231</td>
<td align="left"><code>MISSING_PTYP</code></td>
<td align="left">The payment type is missing. Refer to the <a href="PaymentTypes.html">RIS Payment Types</a></td>
</tr>
<tr class="even">
<td align="left">232</td>
<td align="left"><code>MISSING_CARD</code></td>
<td align="left">The credit card information is missing</td>
</tr>
<tr class="odd">
<td align="left">233</td>
<td align="left"><code>MISSING_MICR</code></td>
<td align="left">Missing Magnetic Ink Character Recognition string</td>
</tr>
<tr class="even">
<td align="left">234</td>
<td align="left"><code>MISSING_PYPL</code></td>
<td align="left">The PayPal Payer ID is missing</td>
</tr>
<tr class="odd">
<td align="left">235</td>
<td align="left"><code>MISSING_PTOK</code></td>
<td align="left">The payment token is missing.</td>
</tr>
<tr class="even">
<td align="left">241</td>
<td align="left"><code>MISSING_IPAD</code></td>
<td align="left">The IP address is missing</td>
</tr>
<tr class="odd">
<td align="left">251</td>
<td align="left"><code>MISSING_MACK</code></td>
<td align="left">The merchant acknowledgement is missing</td>
</tr>
<tr class="even">
<td align="left">261</td>
<td align="left"><code>MISSING_POST</code></td>
<td align="left">The RIS query submitted to Kount contained no data</td>
</tr>
<tr class="odd">
<td align="left">271</td>
<td align="left"><code>MISSING_PROD_TYPE</code></td>
<td align="left">The shopping cart data array attribute is missing.</td>
</tr>
<tr class="even">
<td align="left">272</td>
<td align="left"><code>MISSING_PROD_ITEM</code></td>
<td align="left">The shopping cart data array attribute is missing.</td>
</tr>
<tr class="odd">
<td align="left">273</td>
<td align="left"><code>MISSING_PROD_DESC</code></td>
<td align="left">The shopping cart data array attribute is missing.</td>
</tr>
<tr class="even">
<td align="left">274</td>
<td align="left"><code>MISSING_PROD_QUANT</code></td>
<td align="left">The shopping cart data array attribute is missing.</td>
</tr>
<tr class="odd">
<td align="left">275</td>
<td align="left"><code>MISSING_PROD_PRICE</code></td>
<td align="left">The shopping cart data array attribute is missing.</td>
</tr>
<tr class="even">
<td align="left">301</td>
<td align="left"><code>BAD_VERS</code></td>
<td align="left">The version of Kount supplied by merchant does not fit the four integer parameter</td>
</tr>
<tr class="odd">
<td align="left">302</td>
<td align="left"><code>BAD_MODE</code></td>
<td align="left">The mode type is invalid. Refer to the RIS Inquiry Service Modes: <a href="sdkpython.html#kount-inquiry-module">inquiry</a></td>
</tr>
<tr class="even">
<td align="left">303</td>
<td align="left"><code>BAD_MERC</code></td>
<td align="left">The six digit Merchant ID is malformed or wrong</td>
</tr>
<tr class="odd">
<td align="left">304</td>
<td align="left"><code>BAD_SESS</code></td>
<td align="left">The unique session ID is invalid. Refer to the <a href="Data-Collector.html">Data Collector</a></td>
</tr>
<tr class="even">
<td align="left">305</td>
<td align="left"><code>BAD_TRAN</code></td>
<td align="left">Transaction ID number is malformed</td>
</tr>
<tr class="odd">
<td align="left">311</td>
<td align="left"><code>BAD_CURR</code></td>
<td align="left">The currency was wrong in the RIS submission</td>
</tr>
<tr class="even">
<td align="left">312</td>
<td align="left"><code>BAD_TOTL</code></td>
<td align="left">The total amount is wrong. <code>TOTL</code> is the whole number amount charged to customer</td>
</tr>
<tr class="odd">
<td align="left">321</td>
<td align="left"><code>BAD_EMAL</code></td>
<td align="left">The email address does not meet required format or is greater than 64 characters in length</td>
</tr>
<tr class="even">
<td align="left">322</td>
<td align="left"><code>BAD_ANID</code></td>
<td align="left">For <code>MODE = P</code> RIS inquiries the caller ID is malformed</td>
</tr>
<tr class="odd">
<td align="left">323</td>
<td align="left"><code>BAD_SITE</code></td>
<td align="left">The website identifier that was created in the Agent Web Console (<code>DEFAULT</code> is the default w website ID) does not match what was created in the AWC.</td>
</tr>
<tr class="even">
<td align="left">324</td>
<td align="left"><code>BAD_FRMT</code></td>
<td align="left">The specified format is wrong. Format options are key value pairs, XML, JSON, YAML</td>
</tr>
<tr class="odd">
<td align="left">331</td>
<td align="left"><code>BAD_PTYP</code></td>
<td align="left">The payment type is wrong. Refer to the <a href="PaymentTypes.html">RIS Payment Types</a></td>
</tr>
<tr class="even">
<td align="left">332</td>
<td align="left"><code>BAD_CARD</code></td>
<td align="left">The credit card information is malformed or wrong, test cards do not work in the production environment</td>
</tr>
<tr class="odd">
<td align="left">333</td>
<td align="left"><code>BAD_MICR</code></td>
<td align="left">Malformed or improper Magnetic Ink Character Recognition string.</td>
</tr>
<tr class="even">
<td align="left">334</td>
<td align="left"><code>BAD_PYPL</code></td>
<td align="left">The PayPal Payer ID is malformed or corrupt.</td>
</tr>
<tr class="odd">
<td align="left">335</td>
<td align="left"><code>BAD_GOOG</code></td>
<td align="left">Malformed or improper Google Checkout Account ID string.</td>
</tr>
<tr class="even">
<td align="left">336</td>
<td align="left"><code>BAD_BLML</code></td>
<td align="left">Malformed or improper Bill Me Later account number.</td>
</tr>
<tr class="odd">
<td align="left">337</td>
<td align="left"><code>BAD_PENC</code></td>
<td align="left">The encryption method specified is wrong.</td>
</tr>
<tr class="even">
<td align="left">338</td>
<td align="left"><code>BAD_GDMP</code></td>
<td align="left">The GreenDot payment token is not a valid payment token</td>
</tr>
<tr class="odd">
<td align="left">339</td>
<td align="left"><code>BAD_HASH</code></td>
<td align="left">When payment type equals <code>CARD</code>, <code>PTYP = CARD</code> and payment encryption type equals <code>KHASH</code>, <code>`PENC = KHASH</code> the value must be 20 characters in length.</td>
</tr>
<tr class="even">
<td align="left">340</td>
<td align="left"><code>BAD_MASK</code></td>
<td align="left">Invalid or excessive characters in the <code>PTOK</code> field</td>
</tr>
<tr class="odd">
<td align="left">341</td>
<td align="left"><code>BAD_IPAD</code></td>
<td align="left">The IP address does not match specifications</td>
</tr>
<tr class="even">
<td align="left">342</td>
<td align="left"><code>BAD_GIFT</code></td>
<td align="left">The Gift Card payment token is invalid due to invalid characters, null, or exceeding character length</td>
</tr>
<tr class="odd">
<td align="left">351</td>
<td align="left"><code>BAD_MACK</code></td>
<td align="left">The merchant acknowledgement must be <code>Y</code> or <code>N</code></td>
</tr>
<tr class="even">
<td align="left">362</td>
<td align="left"><code>BAD_CART</code></td>
<td align="left">There is a discrepancy in the shopping cart key count and the number of items actually being sent in the cart</td>
</tr>
<tr class="odd">
<td align="left">371</td>
<td align="left"><code>BAD_PROD_TYPE</code></td>
<td align="left">The shopping cart data array attribute is missing.</td>
</tr>
<tr class="even">
<td align="left">372</td>
<td align="left"><code>BAD_PROD_ITEM</code></td>
<td align="left">The shopping cart data array attribute is corrupt or missing.</td>
</tr>
<tr class="odd">
<td align="left">373</td>
<td align="left"><code>BAD_PROD_DESC</code></td>
<td align="left">The shopping cart data array attribute is corrupt or missing.</td>
</tr>
<tr class="even">
<td align="left">374</td>
<td align="left"><code>BAD_PROD_QUANT</code></td>
<td align="left">The shopping cart data array attribute is corrupt or missing.</td>
</tr>
<tr class="odd">
<td align="left">375</td>
<td align="left"><code>BAD_PROD_PRICE</code></td>
<td align="left">The shopping cart data array attribute is corrupt or missing.</td>
</tr>
<tr class="even">
<td align="left">399</td>
<td align="left"><code>BAD_OPTN</code></td>
<td align="left">A UDF has been mistyped or does not exist in the Agent Web Console</td>
</tr>
<tr class="odd">
<td align="left">401</td>
<td align="left"><code>EXTRA_DATA</code></td>
<td align="left">RIS keys submitted by merchant were not part of SDK</td>
</tr>
<tr class="even">
<td align="left">404</td>
<td align="left"><code>UNNECESSARY_PTOK</code></td>
<td align="left">When <code>PTYP</code> equals <code>NONE</code> and a <code>PTOK</code> is submitted</td>
</tr>
<tr class="odd">
<td align="left">413</td>
<td align="left"><code>REQUEST_ENTITY_TOO_ LARGE</code></td>
<td align="left">The RIS Post to Kount exceeded the 4K limit.</td>
</tr>
<tr class="even">
<td align="left">501</td>
<td align="left"><code>UNAUTH_REQ</code></td>
<td align="left">Error regarding certificate - Using test certificate in prod</td>
</tr>
<tr class="odd">
<td align="left">502</td>
<td align="left"><code>UNAUTH_MERC</code></td>
<td align="left">Invalid Merchant ID has been entered</td>
</tr>
<tr class="even">
<td align="left">601</td>
<td align="left"><code>SYS_ERR</code></td>
<td align="left">Unspecified system error - Contact Merchant Services</td>
</tr>
<tr class="odd">
<td align="left">602</td>
<td align="left"><code>SYS_NOPROCESS</code></td>
<td align="left">Kount will not process particular transaction</td>
</tr>
<tr class="even">
<td align="left">701</td>
<td align="left"><code>NO_HDR</code></td>
<td align="left">No header found with <code>merchantId = [XXXXX]</code>, <code>session_id = [htot2kk5khpamo45f777q455]</code>, <code>trans=[122347]</code> This error occurs when a RIS request goes to the database and there is no data available in the reply. The Update post had an invalid transaction ID#. Check all required fields for update post and confirm they are being passed correctly.</td>
</tr>
</tbody>
</table>

-   **Missing**: When this designation appears, the customer has failed to complete a required field.
-   **Bad**: When this designation appears, some data was sent but failed to meet specifications. This could also be explained as malformed data or bad code that did not meet specifications, such as `AVS = W` instead of `AVS = M`.

