---
title: Session ID Discussion
subtitle:
tags: [features]
author: Jarrett
---

Session ID Details
* Data Collector should be run once for each user’s session within the web browser.
* Session IDs must be unique per request. They must be unique for a minimum of 30 days.
* Session ID values must be alpha-numeric values (0-9, a-z or A-Z). Dashes (-) and underscores (_)
are acceptable.
* Session ID values should be 32 characters in length. Session ID values of less than 32 characters
will be accepted, but it is strongly recommended to use a 32 character value. Note: 32
characters is the maximum number of characters, an error will be thrown if the Session ID
exceeds 32 characters.
