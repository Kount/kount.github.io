---
title: Device Data Collector FAQ 
subtitle: Frequently asked about the Kount Data Collector. 
tags: [data collector, device, FAQ]
---

### The information on this site has moved to [support.kount.com](support.kount.com). Please update any bookmarks and note that this site will be taken down November 30th. Using the information found on this site might cause unexpected results.


#### FAQ's
{:.no_toc}
* TOC
{:toc}


#### Q: Where do I get the Merchant ID?
A Sandbox Boarding Information document will be sent following the initial kick-off call. It contains the Merchant ID and URLs associated with the DC and RIS processes. A separate document for production will be sent with the production service URLs once the test transactions are certified.

#### Q: How do I receive a login to the Agent Web Console?
Kount will create the initial administrator user. Once the user has been created, an automated e-mail will be sent requesting a password creation.

#### Q: Should I send production traffic to the test environment?
Production traffic should not be sent to the test environment due to the possibility of skewed scoring from the test orders.

#### Q: Where should I place the Javascript on my website?
On any webpage prior to the completion of the order, typically somewhere in the order summary or checkout process. This could be different if various payment methods take the customer “off of the site” prior to completion of the order.

#### Q: What does the session identifier do?
The session identifier is used to join the device data with the order data sent to the RIS service. When the RIS process posts data to Kount it must use the session identifier that was created when the customer initiated the Data Collection.

#### Q: Does the session identifier need to be unique?
Yes, the session identifier must be unique over a thirty-day period. If there are duplicate session identifiers, device data originating from the Data Collection process may be erroneously connected to RIS order data. See Session ID Discussion for more information.

#### Q: Are there limitations on the session identifier?
Yes, it must be alpha-numeric, a minimum of 10, and a maximum of 32 characters long. Dashes and underscores are allowed.

#### Q: What should I use for the session identifier?
The merchant may determine what is used, as long as the limitation guidelines are followed. Potential identifiers include the unique web session, UNIX time stamp, and order number appended by time stamp.

#### Q: Have appropriate DNS entries, NATs, and firewall settings been configured correctly?
Due to the security concerns regarding test environments or production environment the merchant’s network operations may need to verify that proper access is available.

#### Q: Does the JavaScript code contain the correct Merchant ID?
Verify that the Merchant ID is the correct ID supplied by Kount.

#### Q: Is the Session ID created in the DC process the same session ID being sent with the RIS post?
Ensure that the Session ID being created and stored during the DC process is the correct one being used in the RIS post to Kount and adheres to the session ID requirements.

#### Q: How do I know the Data Collection process is Successful?
Determine if the process was successful by using Developer Tools within Chrome or Firefox. A successful data collection will be represented by multiple GET/POST requests, including one in which the file, “fin,” indicates the data collection process is complete.

#### Q: How to configure the Data Collector for Phone orders?
Please see <a href='https://kount.github.io/docs/phonetoweb/'>Phone to Web Orders Submissions Page</a>

#### Q: My site does not have any Content Security Policy (CSP) meta tags.  Should I still add them?
No.  If you do not already have CSP meta tags in place, you do not want to use this feature.  This is only for sites who are using CSP tags already, or wish to add more security layers to their site.

#### Q: I added the Content Security Policy (CSP) meta tag and now my site does not work properly.  What do I need to do to fix this?
This is likely due to your site not using meta tags prior to adding ours.  Try removing the meta tag and re-testing (ensuring the Device Data Collector still works)

#### Q: I added the Content Security Policy (CSP) meta tag, but the Device Data Collector no longer works.  What do I need to do to fix this?
Check that the domain name in the CSP settings matches the domain name in the javascript src attribute.  The must be the same for things to work. Other common issues are missing quotes (single ) within the content value, or mis-spelled directives (such as 'unsafe-eval' or img-src). Also ensure there is a semi colon in between each directive.  See the <a href='https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy'>MDN site</a> for more information.
