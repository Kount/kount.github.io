---
title: Email Encryption 
---

## Overview

On June 8th, Kount will switch to mandating encryption on all outbound emails.  You will want to verify if your email server supports STARTTLS.  Go to the following link and enter the domain name of YOUR email address.  <https://starttls-everywhere.org/>

The very first box that checks for STARTTLS should be green.  Note that the remaining boxes about policy and MTA-STS are NOT required to be green in this check.

If you find that you do not support STARTTLS on your mail servers, you will need to notify your E-Mail Administrator to enable the encryption.

Some detail about the Postfix email server for reference. This is not necessarily what your email server type is, it just serves as more technical detail that explains what is being utilized on an email server.  <http://www.postfix.org/TLS_README.html>
