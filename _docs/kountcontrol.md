---
title: Kount Control
subtitle: Digital Account Protection Integration
---

#### Sections in this article

{:.no_toc}
* TOC
{:toc}

## Overview
The following guide is intended to help our Clients quickly understand the scope needed to integrate with Kount’s digital account protection APIs and to provide a high-level overview of integration points and flow.
During integration, Kount will provide support for the Client’s development staff including direct access to Kount’s Solution Engineers. This direct communication is to facilitate quick, accurate responses to integration questions your development team might have.
For detailed technical specifications, SDK, and API documentation can be found at the URLs below.

## Technical Documentation

**Device Data Collector**
* <b><a href='https://kount.github.io/docs/data-collector/'>Browser</a></b>
* <b><a href='https://kount.github.io/docs/dc-sdk/Mobile/'> Mobile</a></b>

**Endpoints**
* <b><a href='https://api-sandbox.kount.com/info/help/'> Info</a></b>
* <b><a href='https://api-sandbox.kount.com/login/help/'> Login</a></b>
* <b><a href='https://api-sandbox.kount.com/events/help/'> Event</a></b>
* <b><a href='https://api-sandbox.kount.com/trusted-device/'> Trusted Device</a></b>

## Environments

Kount has two environments for a Control integration depending on the stage of the implementation:
* Sandbox: Full integration with test data
* Production: Full integration with Production data

A valid Client Identification (clientId) and JWT credentials are required to make a call to any of our API endpoints (JWT credentials are not required for data collection). These credentials will be provided as part of technical integration.

**Sandbox Environment**
The Sandbox Environment is a scaled down replica of the Production Environment and is intended for integration and user testing/setup. The Sandbox Environment will represent all of the functionality of our current Production Environment with the exception of scale. Within the Sandbox environment there is a user interface which the Client’s fraud personnel may login and set Profiles and Policies, research login event history and run reports.

**Production Environment**
The Production Environment is architected to handle full scale production traffic.

## Parameterizing

We recommend parameterizing the variables below to facilitate testing and to ease the move from one environment to another.

**jwt**: This token will be supplied by Kount and will is different from Sandbox to Production. As a parameter, this should facilitate testing.

**apiHost:** The API host will contain the location for the environment the post is being made to:

* Predictive Response Harness and Sandbox: environmentDomain = “api-sandbox”
* Production: environmentDomain = “api”

**version:** While every attempt will be made to not create breaking changes to our API endpoints, we recognize that there may be times when to add new functionality we must make breaking changes. In those events, we will version our API endpoint.

**dataCollectionHost:** It is important to use the proper data collection host to ensure that sessions are properly aligned between data collection and login requests.

* Sandbox: dataCollectionHost = “https://tst.kaptcha.com”
* Production: dataCollectionHost = “https://ssl.kaptcha.com”
