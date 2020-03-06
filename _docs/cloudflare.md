---
title: Cloudflare 
subtitle: Product Update
---

**Overview**
On November 14 , 2019, Kount integrated use of a new provider for DDOS management in our Sandbox and TEST environments in order to ensure protection against DDOS attacks. In order to complete our journey and prior to the Kount deploy of this new service, merchants will need to ensure their servers can communicate to either the RISK or API endpoints. Any merchant using outbound firewall rules that limit communications to the Kount IP address range, is encouraged to remove these and allow access to all addresses.  As many SaaS services move to Cloud based environments, there is an ever growing and changing list of IP addresses that could be in use.  The benefit of adding these rules vs. the effort to maintain them reliably is debatable. If you still feel the need to maintain a list of IP addresses you will want to add them from following list: https://www.cloudflare.com/ips/.  If you choose to maintain IP rules, it is the merchants responsibility to be aware of and update this list whenever Clouldflare changes them.  Kount will not be able to notify you if Cloudflare makes a change to this list.
         

If you currently have the Kount IP address ranges configured for outbound traffic to Kount, you will need to leave them in place for now. Some merchants may also have allowed inbound traffic from the Kount IP range for the Event Notification Service (ENS). You must leave these in place as that traffic will still continue to be sourced from our IP ranges.

**TLS INFORMATION FOR ALL CUSTOMERS:**
* Please ensure your environment supports at least TLS 1.2 and is capable of modern SSL Cipher suites.
{% include alert.html style="primary" text="You most likely already do. Kount currently does not support anything less than TLS 1.2." %}

* Cloudflare provides a matrix of TLS support information here: Cloudflare SSL cipher, browser, and protocol support
* Kount currently supports the same basic cipher list and therefore you should not expect issues during the conversion.  However Cloudflare will update this matrix over time as PCI and other security entities move forward with minimum requirements.  Kount will endeavor to notify of these changes in advance where possible.

**JAVA SPECIFIC ENVIRONMENTS:**
Merchants with **Java** environments must make the following adjustments.





