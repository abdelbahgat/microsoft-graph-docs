---
title: "delegatedPermissionClassification resource type"
description: "Used to specify the classification of a delegated permission."
ms.localizationpriority: medium
doc_type: resourcePageType
ms.prod: "applications"
author: "psignoret"
---

# delegatedPermissionClassification resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Used to specify the classification of a delegated permission.

Delegated permission classifications can be used in combination with user consent settings to choose which permissions a user is allowed to consent to. See [Configure how end-users consent to applications](/azure/active-directory/manage-apps/configure-user-consent) to learn more about permission classifications.

## Properties

| Property | Type | Description |
|:---------------|:--------|:----------|
| id | String | A unique identifier for the **delegatedPermissionClassification** Key. Not nullable. Read-only. |
| classification | permissionClassificationType | The classification value being given. Possible value: `low`. Doesn't support `$filter`. |
| permissionId | Guid | The unique identifier (**id**) for the delegated permission listed in the **publishedPermissionScopes** collection of the [servicePrincipal](servicePrincipal.md). Required on create. Doesn't support `$filter`. |
| permissionName | String | The claim value (**value**) for the delegated permission listed in the **publishedPermissionScopes** collection of the [servicePrincipal](servicePrincipal.md). Doesn't support `$filter`. |

## JSON representation

Here's a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.delegatedPermissionClassification"
}-->

```json
{
  "id": "string (identifier)",
  "classification": "low",
  "permissionId": "string",
  "permissionName": "string"
}
```

