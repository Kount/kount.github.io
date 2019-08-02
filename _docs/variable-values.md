---
title: Variable Values
subtitle:
tags: [feature, data collector]
author: Jarrett
---

|-----------------+------------+-----------------+----------------|
| Default aligned |Left aligned| Center aligned  | Right aligned  |
|-----------------|:-----------|:---------------|---------------|
| First body pardfdt |Second cell | Third cell      | fourth cell    |
| Second line     |foo         | **strong**      | baz            |
| Third line      |quux        | baz             | bar            |
|-----------------+------------+-----------------+----------------|
| Second body     |            |                 |                |
| 2 line          |            |                 |                |
|=================+============+=================+================|
| Footer row      |            |                 |                |
|-----------------+------------+-----------------+----------------|

| VAR                | Description                                                                                                                                                                                                               | Sample                             |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------|
| m                  | Six digit Merchant ID number issued by Kount                                                                                                                                                                              | m=123456                           |
| s                  | 32 character session id; see Session ID Discussion above for more information                                                                                                                                             | s=abcdefg12345abababab123456789012 |
| Data_Collector_URL | The URLs for the Data Collector are Environment specific. There is a URL for Test and a URL for Production. The URL must be obtained from Client Success. Please contact your Client Success Manager or support@kount.com |                                    |
