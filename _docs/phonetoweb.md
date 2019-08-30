---
title: Phone to Web Order Submissions
subtitle: When a merchant submits phone orders via the same web page interface as a customer, the data regarding the merchant’s device is being sent to Kount, not the customer’s device data. This will cause order linking to occur and in time will elevate the score of all orders associated with the persona.
tags: [integration, phone, call center, setup, data collector]
author:
---

>IMPORTANT: 
Linking will also occur if the browser session ID is used as the transaction session ID and
multiple orders are submitted from within the same browser session without closing the browser. This
type of linking can be avoided in three ways:

>* Increment the browser session ID, appending the UNIX timestamp.
>* Choose a different methodology for creating the session ID.
>* Ensure agents close the browser between orders.

#### There are two different methods for receiving phone orders.

1. If the customer service agents navigate to a separate order entry page that does not implement
the Data Collector: Call Center/Phone Orders will be posted as a Mode=P; hard code the IP
address specifically to 10.0.0.1 and provide the phone number within the ANID field (if no phone
number is available, pass 0123456789 hard coded).

2. If the customer service agents navigate to the same page as the customer (executes the Data
Collector): Phone-to-Web Order Submission script example is in Appendix A (to exclude
merchant owned IP addresses that should not be forwarded to Kount), post Call Center Orders
as a Mode=Q; hard code the IP address specifically to 10.0.0.1.

In any of the above circumstances, if the email address is not provided to the agents, the agents will
need to input noemail@Kount.com as the email address to prevent linking.

The scripts found in Appendix A demonstrate configuration examples of excluding merchant-owned IP
addresses that should not be forwarded on to the company’s server.
Required and Optional fields can be found in Appendix B.
