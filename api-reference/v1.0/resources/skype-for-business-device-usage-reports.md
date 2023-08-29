---
title: "Skype for Business device usage reports"
description: "You can use the Skype for Business device usage reports to get details on the types of clients and devices that are used across your organization. These details are very helpful when you are investigating, planning, and making other business decisions for your organization."
ms.localizationpriority: medium
ms.prod: "reports"
author: "sarahwxy"
doc_type: conceptualPageType
---

# Skype for Business device usage reports

Namespace: microsoft.graph

You can use the Skype for Business device usage reports to get details on the types of clients and devices that are used across your organization. These details are very helpful when you are investigating, planning, and making other business decisions for your organization.

> **Note:** For details about different report views and names, see [Microsoft 365 reports - Skype for Business clients used](https://support.office.com/client/Skype-for-Business-clients-used-b9019c36-034f-40c7-acb0-c2a0400b03c3).

## Reports

| Function                                 | Return Type | Description                              |
| :--------------------------------------- | :---------- | :--------------------------------------- |
| [Get user detail](../api/reportroot-getskypeforbusinessdeviceusageuserdetail.md) | Stream      | Get details about Skype for Business device usage by user. |
| [Get distribution user counts](../api/reportroot-getskypeforbusinessdeviceusagedistributionusercounts.md) | Stream      | Get the number of users using unique devices in your organization. The report will show you the number of users per device including Windows, Windows phone, Android phone, iPhone, and iPad. |
| [Get user counts](../api/reportroot-getskypeforbusinessdeviceusageusercounts.md) | Stream      | Get the usage trends on how many users in your organization have connected using the Skype for Business app. You will also get a breakdown by the type of device (Windows, Windows phone, Android phone, iPhone, or iPad) on which the Skype for Business client app is installed and used across your organization. |

