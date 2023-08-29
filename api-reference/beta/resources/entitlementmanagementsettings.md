---
title: "entitlementManagementSettings resource type"
description: "Represents tenant-wide settings for Azure AD entitlement management."
ms.localizationpriority: medium
author: "markwahl-msft"
ms.prod: "governance"
doc_type: "resourcePageType"
---

# entitlementManagementSettings resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents settings that control the behavior of [Azure AD entitlement management](entitlementmanagement-overview.md).  This resource does not include the catalog creators setting; to view or change the catalog creators role membership, use the [role assignments](unifiedroleassignment.md) API with the entitlement management RBAC provider.

## Methods

| Method       | Return Type | Description |
|:-------------|:------------|:------------|
| [Get](../api/entitlementmanagementsettings-get.md) | [entitlementManagementSettings](entitlementmanagementsettings.md) | Read the properties of an **entitlementManagementSettings** object. |
| [Update](../api/entitlementmanagementsettings-update.md) | [entitlementManagementSettings](entitlementmanagementsettings.md) | Update the properties of an **entitlementManagementSettings** object. |

## Properties

| Property     | Type        | Description |
|:-------------|:------------|:------------|
|externalUserLifecycleAction|String|One of `None`, `BlockSignIn`, or `BlockSignInAndDelete`. |
|daysUntilExternalUserDeletedAfterBlocked|Int64|If **externalUserLifecycleAction** is `BlockSignInAndDelete`, the number of days after an external user is blocked from sign in before their account is deleted.|

## Relationships

None.

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.entitlementManagementSettings",
  "keyProperty": ""
}-->

```json
{
  "externalUserLifecycleAction": "String",
  "daysUntilExternalUserDeletedAfterBlocked": 1
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "entitlementManagementSettings resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->


