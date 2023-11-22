---
title: "userIdentity resource type"
description: "In the context of a Microsoft Entra audit log, the resource represents the user information that initiated or was affected by an audit activity."
ms.localizationpriority: medium
author: "dhanyahk"
ms.prod: "users"
doc_type: resourcePageType
---

# userIdentity resource type

Namespace: microsoft.graph

In the context of a Microsoft Entra audit log, the resource represents the user information that initiated or was affected by an audit activity.

## Properties

| Property	   | Type	|Description|
|:---------------|:--------|:----------|
| displayName | String | The identity's display name. This may not always be available or up-to-date.    |
| id          | String | Unique identifier for the identity.  |
| ipAddress   | String| Indicates the client IP address used by user performing the activity (audit log only).|
| userPrincipalName | String  | The userPrincipalName attribute of the user. |

>**Note:** In some cases, the unique identifier might not be available. In this case, the **displayName** property for the identity will be returned, but the **id** property will be missing from the resource.

## JSON representation

Here's a JSON representation of the type.

<!-- {
  "blockType": "resource",
  "optionalProperties": [
"displayName", "thumbnails"
  ],
  "@odata.type": "microsoft.graph.userIdentity"
}-->

```json
{
  "displayName": "string",
  "id": "string",
  "ipAddress": "string",
  "userPrincipalName": "string"
}

```

<!--
{
  "type": "#page.annotation",
  "description": "userIdentity type",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->
