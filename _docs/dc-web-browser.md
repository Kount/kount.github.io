---
title: Web Client and Browser Setup
subtitle: 
tags: [integration, kaxsdc, data collector, setup, code, client sdk]
author:
---

#### Sections in this article
{:.no_toc}
* TOC
{:toc}

## Overview
The Device Data Collector runs on a client’s browser and collects a variety of information that helps uniquely identify the device. 

## High Level Integration Steps

<ol class="uk-list uk-list-divider">
	<li>Download the Kount Device Data Collector SDK</li>
	<li>Optionally add a Content Security Policy</li>
	<li>Configure the Trigger</li>
	<li>Configure the Client</li>
</ol>

## Download the Kount Device Data Collection SDK
The Kount Device Data Collection SDK is hosted by Kount, and needs to be downloaded dynamically to be used on a web page.  

The following code can be used to download the SDK:

```html
<script 
	type='text/javascript' 
	src='https://DATA_COLLECTOR_URL/collect/sdk?
		m=123456&
		s=abcdefg12345abababab123456789012'> 
</script>
```
where:
<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;border-color:#ccc;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 20px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#fff;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 20px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#f0f0f0;}
.tg .tg-9qtj{background-color:#193d68;color:#ffffff;text-align:center;vertical-align:top}
.tg .tg-baqh{text-align:center;vertical-align:top}
.tg .tg-buh4{background-color:#f9f9f9;text-align:left;vertical-align:top;}
.tg .tg-i5ij{background-color:#193d68;color:#ffffff;text-align:left;vertical-align:top}
.tg .tg-dzk6{background-color:#f9f9f9;text-align:center;vertical-align:top}
.tg .tg-0lax{text-align:left;vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-9qtj">﻿VAR</th>
    <th class="tg-i5ij">Description</th>
  </tr>
  <tr>
    <td class="tg-dzk6">m</td>
    <td class="tg-buh4">Six digit Merchant ID number issued by Kount.</td>
  </tr>
  <tr>
    <td class="tg-baqh">s</td>
    <td class="tg-0lax">32 character session ID <br>
    <br>
    Exclude this parameter from the call to the download of the SDK to have Kount generate a session ID for you.
    
   See <a href='https://kount.github.io/docs/session-id/'>session ID</a> discussion in this documentation for more information.</td>
  </tr>
  <tr>
    <td class="tg-dzk6">DATA\_COLLECTOR\_URL</td>
    <td class="tg-buh4">The URLs for the Data Collector are Environment specific. There is a URL for Test and a URL for Production. The URL must be obtained from Client Success.Please contact your Client Success Manager or support@kount.com</td>
  </tr>
</table>

## Content Security Policy
If your organization has instituted a Content Security Policy on your website that interferes with the execution of the Device Data Collection on your site, you will need to add this to your page.  

Please refer to the documentation, or reach out to your Kount technical resource for assistance.

## Configure the Trigger
The Device Data Collector SDK collection process is triggered asynchronously by the 'load' data-event. This gives the collector the most available time to complete its work. The collection is bound to the page load event by adding the kaxsdc class and data-event=‘load’ to an HTML element, such as the HTML body or a div.  It looks something like this:

`<body class='kaxsdc' data-event='load'>`

> **_NOTE:_** To see this in context, refer to the [code example](#code-example) below...

## Configure the Client

The Kount collector JavaScript is namespaced under the ka JavaScript object. It is required to have the above /collect/sdk script tag added to your page, which will import the Device Data Collector SDK. 

To start using the Device Data Collector SDK:

* <b>Create a new ClientSDK object</b>

`var client = new ka.ClientSDK();`

* <b>Optionally Setup Callback Methods</b>
<p>The SDK provides a client programmable callback system that allows the client to execute custom code at certain points in the data collection process. This method allows a merchant to add a callback function to be called at a specified life-cycle hook. A merchant can pass a JavaScript object containing one or more life cycle hooks with a function pointer or an anonymous function to be executed.</p>
<p>List of hooks (In order of firing):</p>
<ul>
<li>collect-begin - Triggers when the collection starts</li>
<li>collect-end - Triggers when the collection ends</li>
</ul>
<p>When executed, the callback function is passed a JavaScript object containing
the following properties:</p>
<ul>
<li>MercSessId – The session ID used in the collection</li>
<li>MerchantId – The merchant Id</li>
</ul>


``` html
client.setupCallback(
    {
        'collect-end':
            function(params) {
                loginButton = document.getElementById('login_button');
                loginButton.removeAttribute('disabled');
            },

        'collect-begin':
            function(params) {
                var loginForm = document.forms['loginForm'];
                var input = document.createElement('input');
                input.type = 'hidden';
                input.name = 'kaId';
                input.value = params['MercSessId'];
                loginForm.appendChild(input);
            }
    }
```


> **_NOTE:_** To see this in context, refer to the [code example](#code-example) below...

* <b>Auto Load Events</b>
<p>Call the autoLoadEvents method on the client to attach the collection process to be automatically triggered by the page elements load event with the className “kaxsdc" configured in Step 3.</p>

`client.autoLoadEvents();`

> **_NOTE:_** To see this in context, refer to the [code example](#code-example) below...

## Code Example

This code is an example of where each of the components discussed above appear in the web page.  Use this example to help you understand where to best integrate into your website.

> **_NOTE:_**  It is recommended that the Data Collector code exist at the top of the page load so it has adequate time to run before a user finishes their interaction with the webpage.

```html
<html>
	
<head>

</head>


   <!-- Adding the data-event=load to the class kaxsdc will start the Client in the autoload.  
        Note - this may be added to different data elements like a div -->

   <body class='kaxsdc' data-event='load'>


   <!-- Get the Collector SDK.  In the example, `DATA_COLLECTOR_URL`, 'm=123456' and 
        s=abcdefg12345abababab123456789012 are placeholder values.  Both 
        DATA_COLLECTOR_URL and the "m" values will be supplied by your Kount Client 
        Success Manager.  The "s" value will be the dynamic session of your customer 
        and should be a variable representing the customer's current session ID.  If
        this parameter is excluded, the SDK will generate a session ID for you. -->
 
   <script type='text/javascript' src='https://DATA_COLLECTOR_URL/collect/sdk?m=123456&
      s=abcdefg12345abababab123456789012'> </script>




      <!-- The following script starts the ClientSDK for the collection.  -->
      <!-- You may optionally setup callbacks for the collect-begin and the
           collect-ends events.  These callbacks can be useful if a business wants to be sure          			 that the collection has completed before asking for a risk evaluation (or to
           know that a risk evaluation is being made with or without a complete set of 
           information)  --> 

      <script type='text/javascript'>
        var client=new ka.ClientSDK();
 
       // OPTIONAL
        client.setupCallback(
            {
                // fires when collection has finished - this example would not enable the 
                // login button until collection has completed
                'collect-end':
                    function(params) {
                        // enable login button
                        loginButton = document.getElementById('login_button');
                        loginButton.removeAttribute('disabled');
                        // now user can login and navigate away from the page
                    },
                    
                // fires when collection has started. 
                'collect-begin':
                    function(params) {
                        // add hidden form element to post session id
                        var loginForm = document.forms['loginForm'];
                        var input = document.createElement('input');
                        input.type = 'hidden';
                        input.name = 'kaId';
                        input.value = params['MercSessId'];
                        loginForm.appendChild(input);
                    }
            }
        );
        // END OPTIONAL SECTION

        // The auto load looks for an element with the 'kaxsdc' class and
        // data-event equal to a DOM event (load in this case). Data collection begins
        // when that event fires on that element--immediately in this example

        client.autoLoadEvents();
      </script>
   </body>
</html>
```
