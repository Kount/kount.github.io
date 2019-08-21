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

The Data Collector runs on a client’s browser and collects a variety of information that helps uniquely identify the device. Add the `<script>` tag to the web page where you want to trigger the Data Collection. The variables are found in Variable Values table on the Session ID Discussion page. Below is sample code.

## High Level Integration Steps

<ul class="uk-list uk-list-divider">
    <li>1. Update the Content Security Policy to the header of the page.</li>
    <li>2. Add the load event to the class kaxsdc in the BODY (this may be attached to a different html
element).</li>
    <li>3. Add the Script tag with the correct Data Collection URL, Merchant ID and Session value.</li>
    <li>4. Set the ka.ClientSDK to autorun when kaxsdc class loads.</li>
</ul>

## Create the kaxsdc Class

The Client Collector SDK data collection process is triggered by the 'load' data-event. This gives the
collector the most available time to complete its work. The collection is bound to the page load event by
adding the kaxsdc class and data-event=‘load’ to an HTML element, such as the HTML body or a div.
(Code example below).

{% include alert.html style="success" text="NOTE: Responsible for triggering data collection."%}


## Namespace & ka.ClientSDK Object

The Kount collector JavaScript is namespaced under the ka JavaScript object. It is required to have the
above /collect/sdk script tag into your page, which will import the Client Collector SDK. To start using
the Client Collector SDK, create a new ClientSDK object: `var client = new ka.ClientSDK()`; (Code example
below).

## Available methods in the ka.ClientSDK object

<ul uk-accordion="multiple: true">
    <li class="uk-closed">
        <a class="uk-accordion-title" href="#">autoLoadEvents()</a>
        <div class="uk-accordion-content">
            <p>Attaches the collection process to be automatically triggered by the page
elements load event with the className “kaxsdc.”</p>
        </div>
    </li>
    <li>
        <a class="uk-accordion-title" href="#">setupCallback(config) </a>
        <div class="uk-accordion-content">
            <p>(OPTIONAL) A client programmable callback system that allows the client to
execute custom code at certain points in the data collection process. This
method allows a merchant to add a callback function to be called at a
specified life-cycle hook. A merchant can pass a JavaScript object containing
one or more life cycle hooks with a function pointer or an anonymous
function to be executed.</p>
<p>List of hooks. (In order of firing)</p>
            <p>• collect-begin - Triggers when the collection starts.</p>
            <p>• collect-end - Triggers when the collection ends.</p>
<p>When executed, the callback function is passed a JavaScript object containing
the following properties:</p>
            <p>• MercSessId – The merchant provided session.</p>
            <p>• MerchantId – The merchant Id.</p>
        </div>
    </li>
</ul>

## Code Example

This code collects device information on page load and includes an optional code
example that will fire an alert when the process reaches the collect-begin and collect-end hooks.

{% include alert.html style="success" text="NOTE: It is recommended that the Data Collector code exist at the top of the page load so it has adequate time to run before a user finishes their interaction with the webpage."%}

```html
1<html>
2<head>
3<!--Following is for Content Security Policy - For more information, please see that
section within this wiki -->
4
5<meta http-equiv="Content-Security-Policy" content="img-src
https://DATA_COLLECTOR_URL; connect-src 'self' 'unsafe-eval' 'unsafe-inline'
https://DATA_COLLECTOR_URL; script-src 'unsafe-eval' 'unsafe-inline'
https://DATA_COLLECTOR_URL; child-src https://DATA_COLLECTOR_URL">
6 <!--Get the Collector SDK. In the example, `DATA_COLLECTOR_URL`, `m=123456` and
`s=abcdefg12345abababab123456789012` are placeholder values. Both DATA_COLLECTOR_URL
and the "m" values will be supplied by your Kount Client Success Manager. The "s"
value will be the dynamic session of your customer and should be a variable
representing the customer's current session ID -->
7
8 <script type='text/javascript'
src='https://DATA_COLLECTOR_URL/collect/sdk?m=123456&s=abcdefg12345abababab12
3456789012'> </script>
9
10 <!--The following script starts the ClientSDK for the collection. OPTIONAL
elements are the callbacks for when the collection starts and when the collection
ends. These callbacks can be useful if a business wants to be sure that the
collection has completed before asking for a risk evaluation (or to know that a risk
evaluation is being made with or without a complete set of information) -->
11
12 <script type='text/javascript'>
13 var client=new ka.ClientSDK();
14
15 // Optional Callback code
16 client.setupCallback(
17 {
18 'collect-end': //Fires when collection has finished; The example below would not enable the Login button until collection has completed
19 function(params) {
20 //Enable login button
21 loginButton =
document.getElementById('login_button');
22 loginButton.removeAttribute('disabled');
23 //Now user can login and navigate away from the page
24 },
25 'collect-begin': //Fires when collection has started
26 function(params) {
27 //Add hidden form element to post session id
28 var loginForm = document.forms['loginForm'];
29 var input = document.createElement('input');
30 input.type = 'hidden';
31 input.name = 'kaId';
32 input.value = params['MercSessId'];
33 loginForm.appendChild(input);
34 }
35 }
36 );
37 //END OPTIONAL SECTION
38 /* The auto load looks for an element with the 'kaxsdc' class and dataevent equal to a DOM event (load in this case). Data collection begins when that event
fires on that element--immediately in this example
39 */
40 client.autoLoadEvents();
41 </script>
42</head>
43<!--Adding the data-event=load to the class kaxsdc will start the Client in The
autoload. Note - this may be added to different data elements like a div -->
44<body class='kaxsdc' data-event='load'>
45
46</body>
47</html>
```
