---
title: "applicationSignInDetailedSummary resource type"
description: "Represents an application sign-in summary."
ms.localizationpriority: medium
author: "egreenberg14"
ms.prod: "identity-and-access-reports"
doc_type: "resourcePageType"
---

# applicationSignInSummary resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents an application sign-in summary.

## Methods

| Method       | Return Type | Description |
|:-------------|:------------|:------------|
| [getAzureADApplicationSignInSummary](../api/reportroot-getazureadapplicationsigninsummary.md) | [applicationSignInSummary](applicationsigninsummary.md) | Read the properties and relationships of an **applicationSignInSummary** object. |

## Properties
| Property     | Type        | Description |
|:-------------|:------------|:------------|
|appDisplayName|String|Name of the application that the user signed into.|
|failedSignInCount|Int64|Count of failed sign-ins made by the application.|
|successPercentage|Int32|Percentage of successful sign-ins made by the application.|
|successfulSignInCount|Int64|Count of successful sign-ins made by the application.|
<!--Hiding this because it's not in the metadata nor in public response objects
|appId|String|  Identifier of the application that the user signed into.|
-->

## Relationships
None


## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.applicationSignInSummary"
}-->

```json
{
  "appDisplayName": "String",
  "appId": "String (identifier)",
  "failedSignInCount": 1024,
  "successPercentage": 1024,
  "successfulSignInCount": 1024
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "applicationSignInSummary resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->


