---
title: Using Content Security Policies(CSP) with the Device Data Collector
subtitle: 
tags: [integration, content security policy, data collector, setup, code]
author:
---

### The information on this site has moved to [support.kount.com](support.kount.com). Please update any bookmarks and note that this site will be taken down November 30th. Using the information found on this site might cause unexpected results.


#### Sections in this article
{:.no_toc}
* TOC
{:toc}

## What is CSP?
Content Security Policy (CSP) is an added layer of security that helps to detect and mitigate certain types of attacks, including Cross-Site Scripting (XSS) and data injection attacks. These attacks are used for everything from data theft to site defacement or distribution of malware. 

From MDN: CSP (Content Security Policy)
Clients who wish to protect their site and their users from certain browser based attacks can include a special HTTP header designed to instruct the browser how best to render and request resources like images, styles, and JavaScript. 


## How is CSP used?
CSP uses the HTTP header Content-Security-Policy with a string containing directives that control the rendering and requesting of resources. This HTTP header can be sent by utilizing server side code (PHP, Java, C#), or with a <meta> tag in the HTML

Example:

```html
<meta http-equiv="Content-Security-Policy" 
	content="default-src 'self'; style-src 'self' 'unsafe-inline'; 
	script-src https://ajax.googleapis.com">`
```

> **_NOTE:_** <b>Use With Caution</b> <br>
> Kount does NOT recommend adding this CSP meta tag to a client's web page unless the client is already using CSP meta tags.  If the client adds this meta tag to a page with no other meta tags, it may disable or stop other 3rd party javascript/iframes and other off site content from working properly.


## How to use CSP with Kount products
While the combinations of CSP directives a merchant might use on their site is dizzying and is based on the unique way their pages are built, a few special directives will be required to ensure that Kount's device fingerprinting works correctly.

* For all Kount products, you should be able to use `https://*.kaptcha.com` as it is the recommended domain for our data collector.  
* However, legacy Kount Access customers may also be using `https://*.kaxsdc.com` which is also still supported.

> **_NOTE:_** <b>Domain Name Matters</b> <br>
> Ensure that the domain name you use in the <meta> tag matches the domain name you use for the `<script>` src attribute.  (i.e. kaptcha.com or kaxsdc.com).  If these values do not match up, the browser will block the downloading and running of the Device Data Collector javascript.

Example META tag with only Kount security settings.  Clients can have multiple CPS meta tags in their page.  As such, adding this line to the `<head>` section of your page will allow the Device Data Collector to run properly on the clients page. 

```html
<meta http-equiv="Content-Security-Policy" 
	content="img-src https://*.kaptcha.com;
	connect-src 'self' 'unsafe-eval' 'unsafe-inline' https://*.kaptcha.com; 
	script-src 'unsafe-eval' 'unsafe-inline' https://*.kaptcha.com; 
	child src https://*.kaptcha.com">
```

* `img-src https://*.kaptcha.com`<br>
Informs the browser that images can be loaded from https://*.kaptcha.com. This is to ensure our logo.gif is loaded.
* `connect-src 'self' 'unsafe-eval' 'unsafe-inline' https://*.kaptcha.com`<br>
This informs the browser to allow downloading of our javascript to create 1st party cookies and inject an (unseen) iframe which runs the collector code
* `script-src 'unsafe-eval' 'unsafe-inline' https://*.kaptcha.com`<br>
Informs the browser that it is safe to run the JavaScript that creates the SDK client, sets up the callbacks, and initiates the data collection.
* `child-src https://*.kaptcha.com`<br> 
Informs the browser that child documents (iframes) can be loaded from https://*.kaptcha.com. This ensures the iframe that does all the work gets loaded.
