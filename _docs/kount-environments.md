---
title: Kount Environments
subtitle: Overview of Kount test and production enviroments.
tags: [setup]
---

Kount has separate environments for test and production. Initial integration for both the Data Collector
and Risk Inquiry Service will take place in the test environment. A boarding document containing
required test environment information will be sent to the merchant.

> The test environment is not engineered to support load testing; it is designed primarily to verify
connectivity and proper data submission. Many features such as order linking, scoring, device location,
and persona related information are limited in the test environment. The following features are not
available or will not display accurately in the test environment:

* Persona orders will not link to merchants across the Kount network.
* Persona Risk Score
* Boost Safety Rating
* Address and phone validation through Melissa Data
* VELO and VMAX
* Network and device information
* Distance calculators
* External services

Test credit cards can be passed into the test environment but will fail in the production environment.
Port 443/HTTPS is required for submission and receipt of Data Collector and Risk Inquiry Service data in
both the test and production environments.

Upon certifying that the correct data is being passed for both the Data Collector and Risk Inquiry Service,
the merchant will be issued a Certification Letter and additional production boarding information. Any
customized data created in the test environment will have to be re-created in the production
environment. This includes users, rules, site IDs, user defined fields, and API Keys.

The test environment will continue to be available for testing purposes but should not be used for
production traffic. Typically, Kount has quarterly releases with new or enhanced features that are
backward compatible. These new features will be available in the test environment, as well.
