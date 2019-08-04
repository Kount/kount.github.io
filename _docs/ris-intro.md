---
title: Risk Inquiry Service (RIS)
tags:
---

<div class="uk-child-width-1-2@s uk-grid-match" uk-grid>
    <div>
        <div class="uk-card uk-card-default uk-card-body">
            <h3 class="uk-card-title">Mode Q</h3>
            <p>Initial queries directed from the merchant to Kount that do not originate from a call center
environment.</p>
        </div>
    </div>
    <div>
        <div class="uk-card uk-card-default uk-card-hover uk-card-body">
            <h3 class="uk-card-title">Mode U</h3>
            <p>Update call to Kount, does not cause a reevaluation of the transaction but will update what is displayed
in the Agent Web Console. This update call does not count towards the number of RIS transactions
purchased. Only certain fields can be updated with MODE=U calls. The PTYP field can only be updated if
the initial post to Kount was PTYP=NONE.</p>
        </div>
    </div>
    <div>
        <div class="uk-card uk-card-default uk-card-hover uk-card-body uk-light">
            <h3 class="uk-card-title">Primary</h3>
            <p>Mode P</p> 
            <ul>
                <li>Initial queries originating from a call center environment.</li>
            </ul>
• IP Address must be hard coded as "10.0.0.1".
• If customer does not provide an e-mail address, use the value EMAL=noemail@Kount.com.
• PayPal is not a valid payment type for MODE=P.</p>
        </div>
    </div>
    <div>
        <div class="uk-card uk-card-default uk-card-hover uk-card-body uk-light">
            <h3 class="uk-card-title">Secondary</h3>
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
        </div>
    </div>
</div>
