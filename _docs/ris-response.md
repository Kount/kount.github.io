---
title: RIS Response
tags:
---

After a merchant has posted RIS information to Kount, a key-value pair string will be returned to the merchant. The RIS response format will be the same that was specified in the RIS post, with the default being named pairs. Each data field must be invoked by ’getter’ methods on the response object found in the SDK. The merchant can then use the RIS response to automate the order management process by keying off the AUTO field and can utilize any of the additional data returned for internal processing.

An important use of the RIS response is the ability to verify if the Data Collector process was successful and view any warnings or errors that were made during the RIS post from the merchant. The KAPT field is used to determine if the Data Collector process was successful. KAPT=Y means successful, KAPT=N means the process was unsuccessful. All warnings will be displayed in the response and if errors do occur the RIS response will be returned with a MODE=E. Appendix C lists all warning and error codes.
