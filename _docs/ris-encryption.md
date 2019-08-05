---
title: RIS Encryption Types
tags:
---

When using the Kount SDK all credit card information, by default, uses the KHASH encryption method
where the credit card information is irreversibly hashed prior to transmission from the merchant to
Kount.

When using the JAVA or .Net SDKs (due to the compiled nature of the languages) KHASH is the only
option for payment encryption. JAVA or .Net environments must use a direct post (outside of the SDK)
method if MASK encryption is chosen.

If not using the SDK the following encryption options are available.

<div class="uk-card uk-card-default uk-card-body uk-width-1-1">
    <h3 class="uk-card-title">KHASH</h3>
    <p>Kount proprietary hash used to hash the credit card number before passing it to Kount. The
hashing algorithm source code can be found in each one of the SDKs or can be requested from Kount.</p>
  <ul>
  <li>PTYP=CARD PENC=KHASH</li>
</ul>
    <p>Output - BIN + 14 alpha-numeric characters.
       Example - 123456A12C34E56G7DFG</P>
</div>

<div class="uk-card uk-card-default uk-card-body uk-width-1-1">
    <h3 class="uk-card-title">MASK</h3>
    <p>Ability to pass the first six and last four of a credit card filled in with XXXs. PENC=MASK is only valid with PTYP=CARD</p>
    <ul>
  <li>PTYP=CARD PENC=MASK</li>
</ul>
    <p>Output BIN + 10 capital “X” characters + Last 4 of credit card. 
       Example - 123456XXXXXXXXXX7890</p>
</div>
