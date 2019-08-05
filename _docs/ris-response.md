---
title: RIS Response
tags:
---

After a merchant has posted RIS information to Kount, a key-value pair string will be returned to the merchant. The RIS response format will be the same that was specified in the RIS post, with the default being named pairs. Each data field must be invoked by ’getter’ methods on the response object found in the SDK. The merchant can then use the RIS response to automate the order management process by keying off the AUTO field and can utilize any of the additional data returned for internal processing.

An important use of the RIS response is the ability to verify if the Data Collector process was successful and view any warnings or errors that were made during the RIS post from the merchant. The KAPT field is used to determine if the Data Collector process was successful. KAPT=Y means successful, KAPT=N means the process was unsuccessful. All warnings will be displayed in the response and if errors do occur the RIS response will be returned with a MODE=E. Appendix C lists all warning and error codes.

### Kount recommends at the minimum the following methods/functions used in the RIS response: 

RIS response Java method examples: 

<table class="tg">
  <tr>
    <td class="tg-0pky">﻿MERC</td>
    <td class="tg-0pky">getMerchantId()</td>
  </tr>
  <tr>
    <td class="tg-gaf0">MODE</td>
    <td class="tg-gaf0">getMode()</td>
  </tr>
  <tr>
    <td class="tg-0pky">TRAN</td>
    <td class="tg-0pky">getTransactionId()</td>
  </tr>
  <tr>
    <td class="tg-btxf">ORDR</td>
    <td class="tg-btxf">getOrderNumber()</td>
  </tr>
  <tr>
    <td class="tg-0pky">AUTO</td>
    <td class="tg-0pky">getAuto()</td>
  </tr>
  <tr>
    <td class="tg-pcvp">SCOR</td>
    <td class="tg-pcvp">getScore()</td>
  </tr>
  <tr>
    <td class="tg-0pky">KAPT</td>
    <td class="tg-0pky">getKaptcha()</td>
  </tr>
  <tr>
    <td class="tg-pcvp">SITE</td>
    <td class="tg-pcvp">getSite()</td>
  </tr>
  <tr>
    <td class="tg-0pky">WARNING</td>
    <td class="tg-0pky">hasWarnings()</td>
  </tr>
  <tr>
    <td class="tg-pcvp"></td>
    <td class="tg-pcvp">getWarningCount()</td>
  </tr>
  <tr>
    <td class="tg-0pky"></td>
    <td class="tg-0pky">getWarnings()</td>
  </tr>
  <tr>
    <td class="tg-pcvp">ERROR</td>
    <td class="tg-pcvp">hasErrors()</td>
  </tr>
  <tr>
    <td class="tg-0pky"></td>
    <td class="tg-0pky">getErrorCount()</td>
  </tr>
  <tr>
    <td class="tg-pcvp"></td>
    <td class="tg-pcvp">getErrors()</td>
  </tr>
  <tr>
    <td class="tg-0pky"></td>
    <td class="tg-0pky">getErrorCodes()</td>
  </tr>
</table>
