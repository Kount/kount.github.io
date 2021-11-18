---
title: Data Collector Troubleshooting
subtitle: Solutions for common Data Collector issues
tags:
---
### The information on this site has moved to [support.kount.com](support.kount.com). Please update any bookmarks and note that this site will be taken down November 30th. Using the information found on this site might cause unexpected results.
#### Troubleshooting
{:.no_toc}
* TOC
{:toc}


#### Q: Have appropriate DNS entries, NATs, and firewall settings been configured correctly?
Due to the security concerns regarding test environments or production environment the merchant’s network operations may need to verify that proper access is available.

#### Q: Does the JavaScript code contain the correct Merchant ID?
Verify that the Merchant ID is the correct ID supplied by Kount.

#### Q: Is the Session ID created in the DC process the same session ID being sent with the RIS post?
Ensure that the Session ID being created and stored during the DC process is the correct one being used in the RIS post to Kount and adheres to the session ID requirements.

#### Q: How do I know the Data Collection process is Successful?
Determine if the process was successful by using Developer Tools within Chrome or Firefox. A successful data collection will be represented by multiple GET/POST requests, including one in which the file, “fin,” indicates the data collection process is complete.
