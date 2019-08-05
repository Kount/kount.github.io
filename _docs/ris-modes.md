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
            <p>IP Address must be hard coded as "10.0.0.1".</p>
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

{% include alert.html style="primary" text="Note that ALL FIELD NAMES for a RIS call must be UPPERCASE. They cannot be other case combinations such as sess, Merc, mOdE. However, the values for fields can be mixed case, such as
SESS=UpperMixedCaseSessID95628." %}
