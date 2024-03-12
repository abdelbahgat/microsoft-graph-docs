---
title: "Skype for Business peer-to-peer activity reports"
description: "You can get details on peer-to-peer activity across your organization. These details are very helpful when you are investigating, planning, and making other business decisions for your organization."
ms.localizationpriority: medium
ms.prod: "reports"
author: "sarahwxy"
doc_type: conceptualPageType
---

# Skype for Business peer-to-peer activity reports

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

You can get details on peer-to-peer activity across your organization. These details are very helpful when you are investigating, planning, and making other business decisions for your organization.

> **Note:** For details about different report views and names, see [Microsoft 365 reports - Skype for Business peer-to-peer activity](https://support.office.com/client/Skype-for-Business-Online-peertopeer-activity-d3b2d569-4ee9-44b8-92bf-d518142f0713).

## Reports

| Function                                                     | CSV return type | JSON return type | Description                                                  |
| :----------------------------------------------------------- | :-------------- | :--------------- | ------------------------------------------------------------ |
| [Get activity counts](../api/reportroot-getskypeforbusinesspeertopeeractivitycounts.md) | Stream          | Stream           | Get usage trends on the number and type of sessions held in your organization. Types of sessions include IM, audio, video, application sharing, and file transfer. |
| [Get user counts](../api/reportroot-getskypeforbusinesspeertopeeractivityusercounts.md) | Stream          | Stream           | Get usage trends on the number of unique users and type of peer-to-peer sessions held in your organization. Types of sessions include IM, audio, video, application sharing, and file transfers in peer-to-peer sessions. |
| [Get minute counts](../api/reportroot-getskypeforbusinesspeertopeeractivityminutecounts.md) | Stream          | Stream           | Get usage trends on the length in minutes and type of peer-to-peer sessions held in your organization. Types of sessions include audio and video. |


