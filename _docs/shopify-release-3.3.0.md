---
layout: page
title: Shopify Release 3.3.0
subtitle: The release notes for the Shopify 3.3.0 deployment. 
tags: [shopify]
---

## Overview
* Auto-Capture Functionality Added
* Auto-Void Functionality Added
* Application Log
* Bug Fixes

## Auto-Capture Functionality

{% include image.html img="shopify-release-3.3.0-capture.png" lightbox="true" alt="Alt for image" %}

If the Auto-Capture box is checked in the configuration of the Kount - Shopify app, an Approve response from Kount will trigger a capture of the outstanding authorization(s) for the order.  This functionality applies for the initial response from Kount as well as an ENS update that moves an order from the Review status to Approve.

> It is important to note that if this functionality is enabled, it is recommended that the merchant updates their payment capture configuration settings to manually capture payments for orders.

{% include image.html img="shopify-release-3.3.0-payment.png" lightbox="true" alt="Alt for image" %}


## Auto-Void Functionality

{% include image.html img="shopify-release-3.3.0-void.png" lightbox="true" alt="Alt for image" %}


If the Auto-Capture box is checked in the configuration of the Kount - Shopify app, a Decline response from Kount will trigger a void of all the outstanding authorization(s) for the order.  This functionality applies for the initial response from Kount as well as an ENS update that moves an order from the Review status to Decline.

> It is important to note that if this functionality is enabled, it is recommended that the merchant updates their payment capture configuration settings to manually capture payments for orders.

{% include image.html img="shopify-release-3.3.0-payment.png" lightbox="true" alt="Alt for image" %}

## Application Log

{% include image.html img="shopify-release-3.3.0-applog.png" lightbox="true" alt="Alt for image" %}


The application log allows the end-user to view high level log messages for Shopify orders that have been handled by the Kount - Shopify app.  The log will contain the last two weeks of transactions processed by the app.  If research needs to be done by orders older than two weeks, please reach out to your customer success manager.

* Order ID - if you have the Shopify Order ID you'd like to research, enter it here and the view will show only the orders with that order ID.

* Log Timestamp - click on the log timestamp field to show all messages that were logged for the selected day.

* Log Level - Select this to show All messages, only Info messages, or only Error messages

* Log Message - type in a string, and the filter will do a wildcard match on that string, only showing the messages that match that pattern.

* Use the pagination control at the bottom of the page to scroll through the application log messages.

## Bug Fixes and Internal Improvements
* Added mapping to include the Shopify account creation date in the Kount Risk assessment
* Fixed a bug where the transaction was being wrongly identified as a Phone order if it initiated from a Third Party application
* Added support for Shopify API Versioning
* Added a webhook handler for Shopify outage notifications
