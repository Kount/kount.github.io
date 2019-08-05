---
title: Risk Inquiry Service Modes
subtitle: Modes are used to specify what type of data is being submitted to Kount.
tags:
---

<div class="uk-child-width-1-2@s uk-grid-match" uk-grid>
    <div>
        <div class="uk-card uk-card-default uk-card-hover uk-card-body">
            <h3 class="uk-card-title">Mode Q</h3>
            <p>Initial queries directed from the merchant to Kount that do not originate from a call center environment.</p>
        </div>
    </div>
    <div>
        <div class="uk-card uk-card-default uk-card-hover uk-card-body">
            <h3 class="uk-card-title">Mode P</h3>
            <p>Initial queries originating from a call center environment.</p>
            <ul>
                <li>IP Address must be hard coded as "10.0.0.1".</li>
                <li>If customer does not provide an e-mail address, use the value EMAL=noemail@Kount.com.</li>
                <li>PayPal is not a valid payment type for MODE=P.</li>
            </ul> 
        </div>
    </div>
    <div>
        <div class="uk-card uk-card-default uk-card-hover uk-card-body">
            <h3 class="uk-card-title">Mode U</h3>
            <p>Update query made after an initial `MODE=Q` or P request and/or any `MODE=U` updates have been made. Updates to certain fields can be made and the transaction will be re-evaluated and return an updated RIS response to the merchant. These updates will be displayed in the Agent Web Console. This query will count towards the number of RIS transactions purchased. The same fields listed in the MODE=U section can be changed for `MODE=X` transactions except for PTYP which is not accepted by `MODE=X`.</p>
        </div>
    </div>
    <div>
        <div class="uk-card uk-card-default uk-card-hover uk-card-body">
            <h3 class="uk-card-title">Mode X</h3>
            <p>Update query made after an initial MODE=Q or P request and/or any MODE=U updates have been made. Updates to certain fields can be made and the transaction will be re-evaluated and return an updated RIS response to the merchant. These updates will be displayed in the Agent Web Console. This query will count towards the number of RIS transactions purchased. The same fields listed in the MODE=U section can be changed for MODE=X transactions except for PTYP which is not accepted by MODE=X.</p>
        </div>
    </div>
</div>

<div class="uk-section uk-section-muted uk-align-center">
    <div class="uk-container">
        <h3>Mode E</h3>
        <div class="uk-grid-match uk-child-width-1-3@m uk-align-center" uk-grid>
            <div>
                <p>Mode E This mode designates an error has occurred and is returned to the merchant in the RIS response.</p>
            </div>
        </div>
    </div>
</div>

{% include alert.html style="success" text="Note that ALL FIELD NAMES for a RIS call must be UPPERCASE. They cannot be other case combinations such as sess, Merc, mOdE. However, the values for fields can be mixed case, such as SESS=UpperMixedCaseSessID95628."%}

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;border-color:#ccc;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 16px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#fff;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 16px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#f0f0f0;}
.tg .tg-9qtj{background-color:#193d68;color:#ffffff;text-align:center;vertical-align:top}
.tg .tg-baqh{text-align:center;vertical-align:top}
.tg .tg-buh4{background-color:#f9f9f9;text-align:left;vertical-align:top}
.tg .tg-dzk6{background-color:#f9f9f9;text-align:center;vertical-align:top}
.tg .tg-0lax{text-align:left;vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-9qtj">﻿Name</th>
    <th class="tg-9qtj">Description</th>
    <th class="tg-9qtj">Character Limit</th>
    <th class="tg-9qtj">Valid Values</th>
    <th class="tg-9qtj">Required&nbsp;&nbsp;&nbsp;&nbsp;</th>
  </tr>
  <tr>
    <td class="tg-dzk6">AUTH</td>
    <td class="tg-buh4">Authorization Status returned to merchant from processor. Acceptable values for the AUTH field are ’A’ for Authorized or ’D’ for Decline. In orders where AUTH=A will aggregate towards order velocity of the persona while orders where AUTH=D will decrement the velocity of the persona.</td>
    <td class="tg-buh4">1</td>
    <td class="tg-buh4">A or D</td>
    <td class="tg-dzk6">No</td>
  </tr>
  <tr>
    <td class="tg-baqh">AVST</td>
    <td class="tg-0lax">Address Verification System Street verification response returned to merchant from processor. Acceptable values are ’M’ for match, ’N’ for no-match, or ’X’ for unsupported or unavailable.</td>
    <td class="tg-0lax">1</td>
    <td class="tg-0lax">M (Match) N (Not a Match) X (Not Available)</td>
    <td class="tg-baqh">No</td>
  </tr>
  <tr>
    <td class="tg-dzk6">AVSZ</td>
    <td class="tg-buh4">Address Verification System Zip Code verification response returned to merchant from processor. Acceptable values are ‘M’ for match, ’N’ for no match, or ‘X’ for unsupported or unavailable.</td>
    <td class="tg-buh4">1</td>
    <td class="tg-buh4">M (Match) N (Not a Match) X (Not Available)</td>
    <td class="tg-dzk6">No</td>
  </tr>
  <tr>
    <td class="tg-baqh">CVVR</td>
    <td class="tg-0lax">Card Verification Value response returned to merchant from processor. Acceptable values are ’M’ for match, ’N’ for no-match, or ’X’ unsupported or unavailable.</td>
    <td class="tg-0lax">1</td>
    <td class="tg-0lax">M (Match)N (Not a Match) X (Not Available)</td>
    <td class="tg-baqh">No</td>
  </tr>
  <tr>
    <td class="tg-dzk6">FRMT</td>
    <td class="tg-buh4">Specifies the format of the RIS response if not using SDK, XML, JSON, YAML</td>
    <td class="tg-buh4">4</td>
    <td class="tg-buh4">SDK, XML, JSON, YAML</td>
    <td class="tg-dzk6">No</td>
  </tr>
  <tr>
    <td class="tg-baqh">LAST4</td>
    <td class="tg-0lax">Last 4 numbers of Credit Card Value</td>
    <td class="tg-0lax">4</td>
    <td class="tg-0lax">Numeric field must be 4 numbers</td>
    <td class="tg-baqh">No</td>
  </tr>
  <tr>
    <td class="tg-dzk6">MACK</td>
    <td class="tg-buh4">Merchants acknowledgement to ship/process the order. The MACK field must be set as ’Y’ if persona data is to be collected to strengthen the score.</td>
    <td class="tg-buh4">1</td>
    <td class="tg-buh4">Y or N</td>
    <td class="tg-dzk6">Yes</td>
  </tr>
  <tr>
    <td class="tg-baqh">MERC</td>
    <td class="tg-0lax">Merchant ID assigned to the merchant by Kount.</td>
    <td class="tg-0lax">6</td>
    <td class="tg-0lax">Numeric field must be 6 numbers</td>
    <td class="tg-baqh">Yes</td>
  </tr>
  <tr>
    <td class="tg-dzk6">MODE</td>
    <td class="tg-buh4">Specifies what mode type the RIS post is: MODE=Q MODE=P MODE=X MODE=U</td>
    <td class="tg-buh4">1</td>
    <td class="tg-buh4">Q, P, X, U</td>
    <td class="tg-dzk6">Yes</td>
  </tr>
  <tr>
    <td class="tg-baqh">ORDR</td>
    <td class="tg-0lax">Merchant’s Order Number</td>
    <td class="tg-0lax">32</td>
    <td class="tg-0lax">Alphanumeric field</td>
    <td class="tg-baqh">No</td>
  </tr>
  <tr>
    <td class="tg-dzk6">PENC</td>
    <td class="tg-buh4">RIS parameter for payment encoding.</td>
    <td class="tg-buh4">KHASH</td>
    <td class="tg-buh4">KHASH OR MASK</td>
    <td class="tg-dzk6">No</td>
  </tr>
  <tr>
    <td class="tg-baqh">PTOK</td>
    <td class="tg-0lax">PTOK value will replace Null value passed in original RIS Post.</td>
    <td class="tg-0lax">32</td>
    <td class="tg-0lax">Value to replace Null value passed in original RIS Post</td>
    <td class="tg-baqh">No</td>
  </tr>
  <tr>
    <td class="tg-dzk6">PTYP</td>
    <td class="tg-buh4">Payment Type submitted by merchant: PYPL BLML GDMP GOOG<br>- NOTE that PTYP must have been set to actual payment PTYP that will be updated within the initial RIS Post. PTOK must have been set to Null. If the PTYP is set to NONE no update can be performed.</td>
    <td class="tg-buh4">4</td>
    <td class="tg-buh4">PYPL, BLML, GDMP, GOOG</td>
    <td class="tg-dzk6">No</td>
  </tr>
  <tr>
    <td class="tg-baqh">RFCB</td>
    <td class="tg-0lax">Refund/Chargeback status: R = Refund C = Chargeback</td>
    <td class="tg-0lax">1</td>
    <td class="tg-0lax">R (Refund) or C (Chargeback)</td>
    <td class="tg-baqh">No</td>
  </tr>
  <tr>
    <td class="tg-dzk6">SESS</td>
    <td class="tg-buh4">Unique Session ID. Must be unique over a 30- day span</td>
    <td class="tg-buh4">32</td>
    <td class="tg-buh4">Alphanumeric field; must be match original RIS Post</td>
    <td class="tg-dzk6">Yes</td>
  </tr>
  <tr>
    <td class="tg-baqh">TRAN</td>
    <td class="tg-0lax">Transaction ID required for update calls to Kount</td>
    <td class="tg-0lax">12</td>
    <td class="tg-0lax">Transaction ID generated by Kount, must match original RIS Post</td>
    <td class="tg-baqh">Yes</td>
  </tr>
  <tr>
    <td class="tg-dzk6">VERS</td>
    <td class="tg-buh4">Specifies version of Kount, built into SDK, must be supplied by the merchant if not using the SDK</td>
    <td class="tg-buh4">4</td>
    <td class="tg-buh4">Version of Kount being used</td>
    <td class="tg-dzk6">Yes</td>
  </tr>
</table>

{% include alert.html style="success" text="NOTE: There are caveats to the PENC, PTOK and PTYP fields. Please contact your Client Success Manager for further details." %}
