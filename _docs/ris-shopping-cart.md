---
title: Shopping Cart Data
subtitle:
tags:
---

Each RIS request must be submitted with a minimum of one shopping cart item. While other RIS data is entered in as key value pairs, shopping cart items must be submitted as an array. Each item is an index in the array, and each index must contain the following five attributes.

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;border-color:#ccc;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#fff;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#f0f0f0;}
.tg .tg-vvcu{background-color:#193d68;color:#ffffff;border-color:inherit;text-align:center;vertical-align:top}
.tg .tg-btxf{background-color:#f9f9f9;border-color:inherit;text-align:left;vertical-align:top}
.tg .tg-0pky{border-color:inherit;text-align:left;vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-vvcu">﻿Attribute</th>
    <th class="tg-vvcu">Type</th>
    <th class="tg-vvcu">Size</th>
    <th class="tg-vvcu">Description</th>
    <th class="tg-vvcu">Example</th>
  </tr>
  <tr>
    <td class="tg-btxf">&nbsp;&nbsp;&nbsp;PROD_TYPE[ ]</td>
    <td class="tg-btxf">String</td>
    <td class="tg-btxf">1-255</td>
    <td class="tg-btxf">High level description of the item.</td>
    <td class="tg-btxf">TV</td>
  </tr>
  <tr>
    <td class="tg-0pky">&nbsp;&nbsp;&nbsp;PROD_ITEM[ ]</td>
    <td class="tg-0pky">String</td>
    <td class="tg-0pky">1-255</td>
    <td class="tg-0pky">Typically, the SKU number for the item.</td>
    <td class="tg-0pky">SKU-2385-42P&nbsp;&nbsp;&nbsp;&nbsp;</td>
  </tr>
  <tr>
    <td class="tg-btxf">&nbsp;&nbsp;&nbsp;PROD_DESC[ ]</td>
    <td class="tg-btxf">String</td>
    <td class="tg-btxf">0-255</td>
    <td class="tg-btxf">Specific description of the item.</td>
    <td class="tg-btxf">42 Inch Plasma&nbsp;&nbsp;&nbsp;&nbsp;</td>
  </tr>
  <tr>
    <td class="tg-0pky">&nbsp;&nbsp;&nbsp;PROD_QUANT[ ]</td>
    <td class="tg-0pky">Integer</td>
    <td class="tg-0pky">Long</td>
    <td class="tg-0pky">The quantity of the item being purchased.</td>
    <td class="tg-0pky">1</td>
  </tr>
  <tr>
    <td class="tg-btxf">&nbsp;&nbsp;&nbsp;PROD_PRICE[ ]</td>
    <td class="tg-btxf">Integer</td>
    <td class="tg-btxf">Long</td>
    <td class="tg-btxf">Price per unit item, displayed in lowest currency factor.</td>
    <td class="tg-btxf">75890</td>
  </tr>
</table>
