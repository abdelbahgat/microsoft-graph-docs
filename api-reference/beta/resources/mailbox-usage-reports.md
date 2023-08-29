---
title: "Mailbox usage reports"
description: "You can get information about users with a mailbox and their level of activity which is primarily based on emails sent and received. You can also see how much storage each mailbox consumes and how many mailboxes are approaching storage quotas."
ms.localizationpriority: medium
author: "sarahwxy"
ms.prod: "reports"
doc_type: conceptualPageType
---

# Mailbox usage reports

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

You can get information about users with a mailbox and their level of activity which is primarily based on emails sent and received. You can also see how much storage each mailbox consumes and how many mailboxes are approaching storage quotas.

> **Note:** For details about different report views and names, see [Microsoft 365 reports - Mailbox usage](https://support.office.com/client/Mailbox-usage-beffbe01-ce2d-4614-9ae5-7898868e2729).

## Reports

| Function                                                     | CSV return type | JSON return type | Description                                                  |
| :----------------------------------------------------------- | :-------------- | :--------------- | ------------------------------------------------------------ |
| [Get mailbox detail](../api/reportroot-getmailboxusagedetail.md) | Stream          | Stream           | Get details about mailbox usage.                             |
| [Get mailbox counts](../api/reportroot-getmailboxusagemailboxcounts.md) | Stream          | Stream           | Get the total number of user mailboxes in your organization and how many are active each day of the reporting period. A mailbox is considered active if the user sent or read any email. |
| [Get quota status mailbox counts](../api/reportroot-getmailboxusagequotastatusmailboxcounts.md) | Stream          | Stream           | Get the count of user mailboxes in each quota category.      |
| [Get storage](../api/reportroot-getmailboxusagestorage.md)   | Stream          | Stream           | Get the amount of storage used in your organization.         |


