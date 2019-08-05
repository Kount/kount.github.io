---
title: Kount Central Modes
subtitle: If you are a Payment Processor using Kount Central, you have access to two additional modes available.
tags:
---

### Mode J (for Kount Central merchants only)

This is a simplified RIS call. It only performs Fraud Manager threshold evaluation for the processor’s specified customer, and does not include Portfolio Manager Rule evaluation or calculation of a Kount Score. This gives Mode J the advantage of increased performance.

#### Mode W (for Kount Central merchants only)

This is basically a standard Mode Q with Mode J response appended to the end. Thresholds are evaluated in addition to Portfolio Manager rules. Mode W has the same input requirements as mode Q, with the addition of CUSTOMER_ID. In a Mode W, the threshold decision/response is appended to the Mode Q decision/response. It is the responsibility of the Processor to evaluate both decisions in a Mode W and take appropriate action. Please see your Merchant Services representative for more information.
