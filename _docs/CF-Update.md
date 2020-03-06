---
Title: Cloudflare
subtilte: Test
---

Cloudflare Github Page:

**GENERAL:**

-        On November 14 , 2019, Kount integrated use of a new provider for DDOS management in our Sandbox and TEST environments in order to ensure protection against DDOS attacks. In order to complete our journey and prior to the Kount deploy of this new service, merchants will need to ensure their servers can communicate to either the RISK or API endpoints. Any merchant using outbound firewall rules that limit communications to the Kount IP address range, is encouraged to remove these and allow access to all addresses.  As many SaaS services move to Cloud based environments, there is an ever growing and changing list of IP addresses that could be in use.  The benefit of adding these rules vs. the effort to maintain them reliably is debatable. If you still feel the need to maintain a list of IP addresses you will want to add them from following list: https://www.cloudflare.com/ips/.  If you choose to maintain IP rules, it is the merchants responsibility to be aware of and update this list whenever Clouldflare changes them.  Kount will not be able to notify you if Cloudflare makes a change to this list.

-         

-        If you currently have the Kount IP address ranges configured for outbound traffic to Kount, you will need to leave them in place for now. Some merchants may also have allowed inbound traffic from the Kount IP range for the Event Notification Service (ENS). You must leave these in place as that traffic will still continue to be sourced from our IP ranges.

**TLS INFORMATION FOR ALL CUSTOMERS:**

-  Please ensure your environment supports at least TLS 1.2 and is capable of modern SSL Cipher suites.

-  Hint: You most likely already do. Kount currently does not support anything less than TLS 1.2.

-  Cloudflare provides a matrix of TLS support information here: Cloudflare SSL cipher, browser, and protocol support

-  Kount currently supports the same basic cipher list and therefore you should not expect issues during the conversion.  However Cloudflare will update this matrix over time as PCI and other security entities move forward with minimum requirements.  Kount will endeavor to notify of these changes in advance where possible.

**JAVA SPECIFIC ENVIRONMENTS:**

-        Merchants with Java environments must make the following adjustments.

-  Any Java version prior to 1.7 is not supported.

-  Ensure you are on the latest version of Java, this should keep your trusted certificate list updated with current root authorities.

-  If you are unable to upgrade Java, you will need to ensure your Java Keystore is up to date with current and modern root authorities.  It is recommended that you keep these updated regularly as root authorities are added and even expire over time. If you do not keep them current you could face security issues or downtime.

-  Digicert root certificates - This contains many of the common root CAs. At minimum you will want the Baltimore CyberTrust Root added to your keystore.

-  Example instructions - An example of how you might update your Java Keystore. You must adjust the command to suit your environment.

-  Ensure that your Java environment has the enableSNIExtension option set to True (which is the default).  Disabling this option will cause you to receive a 403 error from Cloudflare as they are unable to determine which of their hosted services you are attempting to communicate with.

-  Oracle Java Security guide - This document describes details about Java SSL options, including the enableSNIExtension option.

If you're environment is not Java based,

-         

**WHY IS KOUNT MAKING THIS CHANGE:**

We are making the change to Cloudflare because they provide us the following benefits:

-         

-  Distributed Denial of Service (DDoS) protection.

-  More advanced Web Application Firewalling (WAF).

-  More robust TLS/SSL management.

-  Global connectivity which could improve communication speeds to Kount resources.

-  Global Load balancing options.

-  Reachability to Kount services over IPv6.

**WHAT DO I DO NEXT:**

-  Ensure you're submitting test transaction to the Kount TEST/Sandbox environments at https://risk.test.kount.net as this environment is already converted to support CloudFlare and if you're accessing that end point, you're successful

-  We will periodically reach out to you if we have noticed you have not successfully posted any test transactions

-  Inform Kount support if you need additional assistance (support@kount.com) on upgrading your TEST or PROD environments

***Email encryption details for the Github Page:***

On June 8th, Kount will switch to mandating encryption on all outbound emails.  You will want to verify if your email server supports STARTTLS.  Go to the following link and enter the domain name of YOUR email address.  https://starttls-everywhere.org/

The very first box that checks for STARTTLS should be green.  Note that the remains boxes about policy and MTA-STS are NOT required to be green in this check.

If you find that you do not support STARTTLS on your mail servers, you will need to notify your E-Mail Administrator to enable the encryption.

Some detail about the Postfix email server for reference. This is not necessarily what your email server type is, it just serves as more technical detail that explains what is being utilized on an email server.  http://www.postfix.org/TLS_README.html
