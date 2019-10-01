---
title: Invoking the Risk Inquiry Service
tags:
---

# Pre-Authorization
Query Kount before attempting an authorization from the payment gateway, below are the considerations regarding pre-authorization

  * Allows the merchant to avoid processing fees on orders set to “decline” by the merchant.
	* All credit card information can be sent to Kount
  * An update RIS call (MODE=U) must be made to update order number and status of payment authorization including AUTH, AVST, AVSZ, and CVVR data provided by payment gateway
      * For pre-authorization queries set the following required fields as:
        *	MACK=Y
        *	AUTH=A
      * Once the transaction has been processed, update required and additional fields with MODE=U post (see RIS Service Modes section)

#### Pre-Authorization Workflow

{% include image.html img="pre-auth-flow.png" lightbox="true" alt="Alt for image" caption="Pre-Atuh" %}



# Post-Authorization
Query Kount after the payment gateway has been contacted, below are the considerations regarding post-authorization
  
  * All payment gateway information can be passed to Kount (Authorization, AVS, CVV) allowing rules to be created regarding AVS and CVV data.
  * Some payment gateways do not pass credit card data once they have received it
  * Single RIS query, no update is necessary

#### Post Authorization Workflow

{% include image.html img="post-atuh-flow.png" lightbox="true" alt="Alt for image" caption="Post-Auth" %}
