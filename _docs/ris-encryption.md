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

<div class="uk-card uk-card-default uk-card-hover uk-card-body uk-width-1-1">
    <h3 class="uk-card-title">KHASH</h3>
    <p>Kount proprietary hash used to hash the credit card number before passing it to Kount. The
hashing algorithm source code can be found in each one of the SDKs or can be requested from Kount.</p>
  <ul>
  <li>PTYP=CARD PENC=KHASH</li>
</ul>
    <p>Output - BIN + 14 alpha-numeric characters.
       Example - 123456A12C34E56G7DFG</P>
</div>

<hr>

<div class="uk-card uk-card-default uk-card-hover uk-card-body uk-width-1-1">
    <h3 class="uk-card-title">MASK</h3>
    <p>Ability to pass the first six and last four of a credit card filled in with XXXs. PENC=MASK is only valid with PTYP=CARD</p>
    <ul>
  <li>PTYP=CARD PENC=MASK</li>
</ul>
    <p>Output BIN + 9 capital “X” characters + Last 4 of credit card. 
       Example - 123456XXXXXXXXX7890</p>
</div>

{% include alert.html style="success" text="NOTE: The “X” characters must all be capital “X”." %}

{% include alert.html style="danger" text="IMPORTANT: The above example value is just for purposes of illustration. The PTOK should be the samelength as the original card number. You can use the card number with the first 6 and last 4 numerals present and the rest of the numbers in the card masked by “Xs” but the number of characters must be the same as those of the actual card number."%}

