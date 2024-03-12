---
title: "SharePoint activity reports"
description: "You can get the activity of every user licensed to use SharePoint by looking at their interaction with files. You can also look at the level of collaboration going on based on the number of files shared."
ms.localizationpriority: medium
ms.prod: "reports"
author: "sarahwxy"
doc_type: conceptualPageType
---

# SharePoint activity reports

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

You can get the activity of every user licensed to use SharePoint by looking at their interaction with files. You can also look at the level of collaboration going on based on the number of files shared.

> **Note:** For details about different report views and names, see [Microsoft 365 reports - SharePoint activity](https://support.office.com/client/SharePoint-activity-a91c958f-1279-499d-9959-12f0de08dc8f).

## Reports

| Function                                                     | CSV Return Type | JSON Return Type | Description                                                  |
| :----------------------------------------------------------- | :-------------- | :--------------- | ------------------------------------------------------------ |
| [Get user detail](../api/reportroot-getsharepointactivityuserdetail.md) | Stream          | Stream           | Get details about SharePoint activity by user.               |
| [Get file counts](../api/reportroot-getsharepointactivityfilecounts.md) | Stream          | Stream           | Get the number of unique, licensed users who interacted with files stored on SharePoint sites. |
| [Get user counts](../api/reportroot-getsharepointactivityusercounts.md) | Stream          | Stream           | Get the trend in the number of active users. A user is considered active if he or she has executed a file activity (save, sync, modify, or share) or visited a page within the specified time period. |
| [Get pages](../api/reportroot-getsharepointactivitypages.md) | Stream          | Stream           | Get the number of unique pages visited by users.             |


