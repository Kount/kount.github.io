---
title: Session ID 
subtitle: The Session ID is the unique identifier for the collection event and is specific to the user’s request. You will use the Session ID for subsequent calls to the Inquiry Service.
tags: [features]
author: Todd Funke
---

{:.no_toc}
* TOC
{:toc}

## Overview
The Session ID is a critical component of the Kount integration.  It is the data element that allows the Device Collection transaction to be tied to the Risk Assessment (RIS) being done on the transaction.  The same Session ID used for Device Collection must be sent along with the RIS payload.  

> **_NOTE:_**  It is important to understand that the session ID that is used here is not the same concept as a web session.  You must make sure the Session ID used for the integration to Kount is unique per each Kount Risk Assessment transaction.  
> 
> See the [Session ID Requirements](#session-id-requirements) section below for more information.

## Implementation Details
The integration allows for two ways to create a Session ID:

### Let Kount Do it
This method is recommended by Kount.  The value is created by Kount and will be returned when the device data collection SDK is downloaded.  This method ensures the uniqueness of the session ID, and also ensures that it meets the requirements of a valid session ID.  This is accomplished by excluding the session ID parameter in the call to download the Device Data Collection SDK, like this (web implementation only):

```html
<script type='text/javascript' 
	src='https://DATA_COLLECTOR_URL/collect/sdk?m=123456'> 
</script>
``` 
> **_NOTE:_** This option is not available for a native mobile device collection integration.

### Generate your Own 
If you want or need control over the session ID that is passed to Kount, you have the option to generate your own.  This is accomplished by creating the session ID that meets the criteria described below and including that in the call to download the Device Data Collection SDK (web implementation only).  Assuming the session ID used in this example is abcdefg12345abababab123456789012, the call to download the SDK looks like this:

```html
<script type='text/javascript' 
	src='https://DATA_COLLECTOR_URL/collect/sdk?
		m=123456&
		s=abcdefg12345abababab123456789012'> 
</script>
```

### How do I Access my Session ID
Whether you let Kount generate your session ID, or you generate your own, it'll be made availble to the script on the page via the ka.sessionId attribute that is included in the downloaded Device Data Collection SDK.  This is discussed in greater detail on the Web Client and Browser Setup documentation page.

## Session ID Requirements
* Session IDs must be unique per request. They must be unique for a minimum of 30 days.
* Session ID must contain only alphanumeric characters (0-9, a-z or A-Z), or underscores (_).
* Session ID values should be 32 characters in length. Session ID values of less than 32 characters
will be accepted, but it is strongly recommended to use a 32 character value.

> **_NOTE:_** If the Session ID exceeds 32 characters or contains any invalid characters, an error will be thrown when attempting to download the SDK

