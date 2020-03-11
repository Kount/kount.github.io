---
title: Kount Control
subtitle: Digital Account Protection Integration
---

#### Sections in this article

{:.no_toc}

{:toc}

### Overview
The following guide is intended to help our Clients quickly understand the scope needed to integrate with Kount’s digital account protection APIs and to provide a high-level overview of integration points and flow.
During integration, Kount will provide support for the Client’s development staff including direct access to Kount’s Solution Engineers. This direct communication is to facilitate quick, accurate responses to integration questions your development team might have.
For detailed technical specifications, SDK, and API documentation can be found at the URLs below.

### Technical Documentation

**Device Data Collector**
* <b><a href='https://kount.github.io/docs/data-collector/'>Browser</a></b>
* <b><a href='https://kount.github.io/docs/dc-sdk/Mobile/'> Mobile</a></b>

**Endpoints**
* <b><a href='https://api-sandbox.kount.com/info/help/'> Info</a></b>
* <b><a href='https://api-sandbox.kount.com/login/help/'> Login</a></b>
* <b><a href='https://api-sandbox.kount.com/events/help/'> Event</a></b>
* <b><a href='https://api-sandbox.kount.com/trusted-device/'> Trusted Device</a></b>

### Environments

Kount has two environments for a Control integration depending on the stage of the implementation:
* Sandbox: Full integration with test data
* Production: Full integration with Production data

A valid Client Identification (clientId) and JWT credentials are required to make a call to any of our API endpoints (JWT credentials are not required for data collection). These credentials will be provided as part of technical integration.

**Sandbox Environment**
The Sandbox Environment is a scaled down replica of the Production Environment and is intended for integration and user testing/setup. The Sandbox Environment will represent all of the functionality of our current Production Environment with the exception of scale. Within the Sandbox environment there is a user interface which the Client’s fraud personnel may login and set Profiles and Policies, research login event history and run reports.

**Production Environment**
The Production Environment is architected to handle full scale production traffic.

### Parameterizing

We recommend parameterizing the variables below to facilitate testing and to ease the move from one environment to another.

**jwt**: This token will be supplied by Kount and will is different from Sandbox to Production. As a parameter, this should facilitate testing.

**apiHost:** The API host will contain the location for the environment the post is being made to:

* Predictive Response Harness and Sandbox: environmentDomain = “api-sandbox”
* Production: environmentDomain = “api”

**version:** While every attempt will be made to not create breaking changes to our API endpoints, we recognize that there may be times when to add new functionality we must make breaking changes. In those events, we will version our API endpoint.

**dataCollectionHost:** It is important to use the proper data collection host to ensure that sessions are properly aligned between data collection and login requests.

* Sandbox: dataCollectionHost = “https://tst.kaptcha.com”
* Production: dataCollectionHost = “https://ssl.kaptcha.com”

### Data Collection

Kount uses a light-weight data collection to gather information about a device. Data collection is made prior to making a Post to the Login API. The data collection uses the same session identifier as the subsequent login event to tie information together, so special care should be made with sessions to ensure that the data collection and the login event share the same session identification.

For Kount’s browser Data Collector:
* <b><a href='https://kount.github.io/docs/data-collector/'>Browser</a></b>

For Android and iOS SDKs respectively:
* <b><a href='https://kount.github.io/docs/dc-sdk/Mobile/'> Mobile</a></b>

**Browser Recommendations**

Proper placement and configuration of the browser Data Collector is crucial in gathering information to identify devices, adhere to business policy, and accurately define login risk. Incorrect placement or misconfiguration may cause limited or no data collection.

**Page and Page Location**

Suggested placement of the data collection code is in the body of the login page. Kount abates collection from the same session ID when a collection comes within 15 minutes. However, it is strongly recommended care is taken to run a single data collection per session. When multiple collections are run for a single session (if the collection was placed in the header, for example), it is possible the collection events will be mistaken as a DDOS attacked and all collections from your site will be throttled.

**Chrome's Lazy Load**

Chrome’s soon to be released feature “Lazy Load” will defer loading images and iframes that come below the fold of the page. This feature will be active when Chrome’s Data Saver feature is on and when the loading attribute is set to “lazy” or “auto” or unset. More information can be found <a href='https://groups.google.com/a/chromium.org/forum/#!topic/blink-dev/jxiJvQc-gVg'>here</a>.

For Client’s using Kount’s legacy data collector that utilizes an iframe, it is recommended to update integration or set the “loading” attribute to “eager” which will bypass lazy loading functionality.

**Content Security Policy**

Kount utilizes both third party and first party cookies as well as device data to identify devices. In order to take full advantage of the device collector features, Clients may need to make modifications to the Content Security Policy on their site.

For more information on Content Security Policy and settings for the Data Collector, please contact your Kount Solutions Engineer.

### Login Event Workflow

The basic workflow of digital account protection starts with collecting data from the device. When the user logs in with valid credentials, the Client will make a post to Kount’s Login API to get a response of Accept, Block, or Challenge.

Depending on the response based on your policies from Kount, the Client may either allow access, deny access, or challenge their user using their existing step-up authentication.

**Step 1**

The digital account protection workflow begins with a Data Collection (below) from the browser application or from the mobile SDK. Kount’s browser data collector is a light-weight JavaScript SDK downloaded at runtime. Our mobile SDK can be integrated into your mobile application. Only one data collection should be made per session.

**Step 2**

Step 2: After user’s login credentials have been posted to your authentication service, there are two paths:

* Valid Credentials: If the user presented valid credentials, the Client will Post to Kount’s Login Decision API prior to granting access. The response to this API call is Allow, Block, or Challenge.

* Invalid Credentials: If the user fails authentication, the Client will decline access to the user and Post to the failed-attempt API. This API increases velocities and informs Kount’s ML and AI models for future login attempts.

**Step 3**

If the Login decision results in a “Challenge” it is imperative to send the outcome of the login challenge to Kount to better update our AI models and to update information for use within the portal.

**Tehnical Specifications**

The API for the Login Event can be found here:
* <b><a href='https://api-sandbox.kount.com/login/help/'> Login</a></b>

The API for the Failed Attempt and Login Challenge Outcome can be found here: 
* <b><a href='https://api-sandbox.kount.com/events/help/'> Event</a></b>
