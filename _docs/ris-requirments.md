---
title: Risk Inquiry Service Requirements
tags:
---

RIS data posted to Kount must be URL encoded and submitted as key-value pairs. Much of the work can be simplified by utilizing a Kount provided SDK, including URL encoding. Kount provides a Software Development Kit (SDK) for Java, .NET, PHP, Perl, and Mobile environments.

Recommendations regarding each development environment and their supported versions, configuration, logging, and paths are found in the README file located in the “docs“ directory in each respective SDK, please read the documentation associated with each SDK.

<ul class="uk-list uk-list-divider">
    <li>1. Port 443 must be available to post and receive data from Kount.</li>
    <li>2.	API Keys are used to authenticate the RIS HTTPS submission to Kount, (similar to a password). A single API Key will be used for RIS submissions, the key is not subject to expiration date and does not require re-issuance. To generate an API Key, navigate to the ADMIN tab -> API Keys. See the RIS API Keys section of this document for more detailed instructions. Note: API Keys can only be used with Kount version 0630 and newer.</li>
    <li>3.	SSL support is required for the RIS process. TLS version 1.2 is currently supported.</li>
    <li>4.	The session identifier created during the data collector process must be passed as the session identifier for the RIS transaction. This identifier must be unique for at least 30 days. If a single session ID were to be used on multiple transactions, those transactions would link together and erroneously affect the persona information in the risk score.</li>
    <li>5.	RIS posts are limited to a total of 40,960 characters or bytes.</li>
    <li>6.	To utilize the various SDKs, several required static settings must be configured. Please refer to the README files included in each of the SDKs.</li>
</ul>
