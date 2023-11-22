---
title: "teamsAsyncOperation resource type"
description: "A Microsoft Teams async operation is an operation that transcends the lifetime of a single API request. "
author: "nkramer"
ms.localizationpriority: medium
ms.prod: "microsoft-teams"
doc_type: resourcePageType
---

# teamsAsyncOperation resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

A Microsoft Teams async operation is an operation that transcends the lifetime of a single API request. 
These operations are long-running or too expensive to complete within the timeframe of their originating request.

When an async operation is initiated, the method returns a 202 Accepted response code. 
The response will also contain a Location header, which contains the location of the teamsAsyncOperation. 
Periodically check the status of the operation by making a GET request to this location; wait >30 seconds between checks.
When the request completes successfully, the status will be "succeeded" and the targetResourceLocation will point to the created/modified resource.

## Methods

|  Method                                                                   |  Return Type                                                                     | Description                                                       | 
| :------------------------------------------------------------------------ | :------------------------------------------------------------------------------- | :---------------------------------------------------------------- |
| [List operations on a chat](../api/chat-list-operations.md)               | [resourceSpecificPermissionGrant](resourcespecificpermissiongrant.md) collection | List async operations that ran or are running on a specific chat. |
| [Get operation](../api/teamsasyncoperation-get.md)                   | [resourceSpecificPermissionGrant](resourcespecificpermissiongrant.md) collection | Get an async operation that ran or is running on a specific resource. |

## Properties

| Property | Type	| Description |
|:---------------|:--------|:----------|
|id|string |Unique operation id.|
|operationType|[teamsAsyncOperationType](teamsasyncoperationtype.md) |Denotes the type of operation being described. |
|createdDateTime|DateTimeOffset |Time when the operation was created.|
|status|[teamsAsyncOperationStatus](teamsasyncoperationstatus.md)| Operation status.|
|lastActionDateTime|DateTimeOffset |Time when the async operation was last updated.|
|attemptsCount|Int32|Number of times the operation was attempted before being marked successful or failed.|
|targetResourceId|guid |The ID of the object that's created or modified as result of this async operation, typically a [team](../resources/team.md).|
|targetResourceLocation|string|The location of the object that's created or modified as result of this async operation. This URL should be treated as an opaque value and not parsed into its component paths.|
|error|[operationError](operationerror.md)|Any error that causes the async operation to fail.|

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.teamsAsyncOperation"
}-->

```json
{
    "id": "string",
    "operationType": "string",
    "createdDateTime": "string (timestamp)",
    "status": "string",
    "lastActionDateTime": "string (timestamp)",
    "attemptsCount": "Integer",
    "targetResourceId": "string",
    "targetResourceLocation": "string",
    "error": null
}
```

<!-- uuid: 20fd7863-9545-40d4-ae8f-fee2d115a690
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "teams async operation resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


