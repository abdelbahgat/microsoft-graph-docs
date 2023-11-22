---
author: spgraph-docs-team
description: The dateTimeColumn on a columnDefinition resource indicates that the column's values are dates or times.
ms.date: 09/11/2017
title: DateTimeColumn
ms.localizationpriority: medium
doc_type: resourcePageType
ms.prod: sites-and-lists
---

# DateTimeColumn resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

The **dateTimeColumn** on a [columnDefinition](columndefinition.md) resource indicates that the column's values are dates or times.

## JSON representation

Here's a JSON representation of a **dateTimeColumn** resource.

<!-- { "blockType": "resource", "@odata.type": "microsoft.graph.dateTimeColumn" } -->

```json
{
  "displayAs": "default | friendly | standard",
  "format": "dateOnly | dateTime"
}
```

## Properties

| Property      | Type   | Description                                                                                                                                                         |
| :------------ | :----- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **displayAs** | string | How the value should be presented in the UX. Must be one of `default`, `friendly`, or `standard`. See below for more details. If unspecified, treated as `default`. |
| **format**    | string | Indicates whether the value should be presented as a date only or a date and time. Must be one of `dateOnly` or `dateTime`                                          |

## DisplayAs values

| Value        | Description                                                         |
| :----------- | :------------------------------------------------------------------ |
| **default**  | Uses the default rendering in the UX.                               |
| **friendly** | Uses a friendly relative representation (for example "today at 3:00 PM")    |
| **standard** | Uses the standard absolute representation (for example "5/10/2017 3:20 PM") |

<!--
{
  "type": "#page.annotation",
  "description": "",
  "keywords": "",
  "section": "documentation",
  "tocPath": "Resources/DateTimeColumn",
  "suppressions": []
}
-->
