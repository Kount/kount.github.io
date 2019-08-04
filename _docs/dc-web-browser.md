---
title: Web Client and Browser Setup
subtitle:
tags:
author:
---

The Data Collector runs on a client’s browser and collects a variety of information that helps uniquely
identify the device. Add the `<script>` tag to the web page where you want to trigger the Data Collection.
The variables are found in the above table. Below is sample code.

### High Level Integration Steps:

<ul class="uk-list uk-list-divider">
    <li>1. Update the Content Security Policy to the header of the page.</li>
    <li>2. Add the load event to the class kaxsdc in the BODY (this may be attached to a different html
element).</li>
    <li>3. Add the Script tag with the correct Data Collection URL, Merchant ID and Session value.</li>
    <li>4. Set the ka.ClientSDK to autorun when kaxsdc class loads.</li>
</ul>

## Create the kaxsdc Class

{% include alert.html style="primary" text="Responsible for triggering data collection."%}

The Client Collector SDK data collection process is triggered by the 'load' data-event. This gives the
collector the most available time to complete its work. The collection is bound to the page load event by
adding the kaxsdc class and data-event=‘load’ to an HTML element, such as the HTML body or a div.
(Code example below).

## Namespace & ka.ClientSDK Object

The Kount collector JavaScript is namespaced under the ka JavaScript object. It is required to have the
above /collect/sdk script tag into your page, which will import the Client Collector SDK. To start using
the Client Collector SDK, create a new ClientSDK object: var client = new ka.ClientSDK(); (Code example
below).

### Available methods in the ka.ClientSDK object

<ul uk-accordion="multiple: true">
    <li class="uk-open">
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
            </p>- TEst</p>
            </p>- Test</p>
        </div>
    </li>
    <li>
        <a class="uk-accordion-title" href="#">Item 3</a>
        <div class="uk-accordion-content">
            <p>Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat proident.</p>
        </div>
    </li>
</ul>
