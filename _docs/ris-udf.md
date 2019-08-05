---
title: User Defined Fields
tags: [UDF]
---

Kount provides a way for merchants to include additional information related to their business that may not be a standard field in Kount by creating user defined fields. UDFs are created in the Agent Web Console by browsing to the Fraud Control tab and clicking on User Defined Fields. Once you have defined the UDF in the Agent Web Console you will be able to pass this data into Kount via an array called UDF as key-value pairs where the label is the key and the data passed in is the value. The maximum number of UDFs that can be created is 500, and response time for evaluating transactions will degrade as more UDFs are added. There are four data types available for user defined fields.

{% include alert.html style="success" text="NOTE: UDF labels can be up to 28 characters in length and cannot begin with a number."%}

#### UDF Data Types

<ul class="uk-list uk-list-divider">
    <li>1. 1.	Number: This UDF type is not eligible for VIP List options or for Velocity tracking; however, it is available for use in the Kount Rules Engine.</li>
    <li>2. 2.	Alpha-Numeric: This UDF type is eligible for VIP List Management, as well as for tracking Persona Velocities within the Kount Rules Engine. Separate VIP Lists for the values being passed in these UDFs may be created. Additionally, Persona Velocity for a specific value contained within the UDF may be tracked.</li>
    <li>3. 3.	Date: This UDF type is not eligible for VIP List options or for Velocity tracking; however, it is available for use in the Kount Rules Engine.</li>
    <li>4. 4.	Amount: This UDF type is not eligible for VIP List options or for Velocity tracking; however, it is available for use in the Kount Rules Engine.</li>
</ul>
