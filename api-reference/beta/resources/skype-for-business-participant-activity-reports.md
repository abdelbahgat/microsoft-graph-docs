---
title: "Skype for Business participant activity reports"
description: "You can get details on conferencing activity across your organization. These details are helpful when you're investigating, planning, and making other business decisions for your organization."
ms.localizationpriority: medium
ms.prod: "reports"
author: "sarahwxy"
doc_type: conceptualPageType
---

# Skype for Business participant activity reports

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

You can get details on conferencing activity across your organization. These details are helpful when you're investigating, planning, and making other business decisions for your organization.

> **Note:** For details about different report views and names, see [Microsoft 365 reports - Skype for Business conference participant activity](https://support.office.com/client/Skype-for-Business-Online-conference-participant-activity-c3c89995-65dd-4715-9e38-bb244c742c6b).

## Reports

| Function                                                     | CSV return type | JSON return type | Description                                                  |
| :----------------------------------------------------------- | :-------------- | :--------------- | ------------------------------------------------------------ |
| [Get activity counts](../api/reportroot-getskypeforbusinessparticipantactivitycounts.md) | Stream          | Stream           | Get usage trends on the number and type of conference sessions that users from your organization participated in. Types of conference sessions include IM, audio/video, application sharing, web, and dial-in/out - third party. |
| [Get user counts](../api/reportroot-getskypeforbusinessparticipantactivityusercounts.md) | Stream          | Stream           | Get usage trends on the number of unique users and type of conference sessions that users from your organization participated in. Types of conference sessions include IM, audio/video, application sharing, web, and dial-in/out - third party. |
| [Get minute counts](../api/reportroot-getskypeforbusinessparticipantactivityminutecounts.md) | Stream          | Stream           | Get usage trends on the length in minutes and type of conference sessions that users from your organization participated in. Types of conference sessions include audio/video. |


