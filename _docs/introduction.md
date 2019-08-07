---
title: Introduction 
subtitle: An overview of the Kount Platform.
tags: [features]
---

{% include image.html img="kountworkflow.png" lightbox="true" alt="Alt for image" caption="Kount Workflow" %}

Kount aggregates and evaluates data from two primary sources, the Data Collector (DC) and the Risk Inquiry Service (RIS). After collecting and evaluating customer data, Kount returns a string of key-value pairs to the merchant. Order-related data is also displayed in the Agent Web Console accessible via a secured merchant login over the Internet.

The Data Collector gathers information from a customer’s device by redirecting the device browser momentarily to Kount then back to the merchant. This passive analysis obfuscates Kount’s interaction with the customer and does not affect the customer’s purchasing experience.

The Risk Inquiry Service evaluates the data provided by the Data Collector and the order-form data submitted from the merchant to create a fraud score. Merchant specified rules are also assessed for each transaction during this evaluation process. Once an order has been evaluated, a response string of key value pairs is returned to the merchant including a score, device fingerprint, and an automated response code. Upon receipt of this response data the merchant can disposition orders based upon specified rules.

{% include image.html img="msv2.pdf" lightbox="true" alt="Alt for image" caption="Image in lightbox" %}
