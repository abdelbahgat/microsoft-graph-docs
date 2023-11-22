---
title: "Skype for Business activity reports"
description: "You can get details on activity across your organization. These details can help you investigate, plan, and make other business decisions for your organization."
ms.localizationpriority: medium
ms.prod: "reports"
author: "sarahwxy"
doc_type: conceptualPageType
---

# Skype for Business activity reports

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

You can get details on activity across your organization. These details can help you investigate, plan, and make other business decisions for your organization.

> **Note:** For details about different report views and names, see [Microsoft 365 reports - Skype for Business activity](https://support.office.com/client/Skype-for-Business-Online-activity-8cbe2eb2-1194-4fd7-b1ee-9f9287c82424).

## Reports

| Function                                                     | CSV return type | JSON return type | Description                                                  |
| :----------------------------------------------------------- | :-------------- | :--------------- | ------------------------------------------------------------ |
| [Get user detail](../api/reportroot-getskypeforbusinessactivityuserdetail.md) | Stream          | Stream           | Get details about Skype for Business activity by user.       |
| [Get activity counts](../api/reportroot-getskypeforbusinessactivitycounts.md) | Stream          | Stream           | Get the trends on how many users organized and participated in conference sessions held in your organization through Skype for Business. The report also includes the number of peer-to-peer sessions. |
| [Get user counts](../api/reportroot-getskypeforbusinessactivityusercounts.md) | Stream          | Stream           | Get the trends on how many unique users organized and participated in conference sessions held in your organization through Skype for Business. The report also includes the number of peer-to-peer sessions. |


