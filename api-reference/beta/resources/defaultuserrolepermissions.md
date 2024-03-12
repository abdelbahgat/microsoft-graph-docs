---
title: "defaultUserRolePermissions resource type"
description: "Contains certain customizable permissions of default user role."
ms.localizationpriority: medium
author: "DougKirschner"
ms.prod: "identity-and-sign-in"
doc_type: "resourcePageType"
---

# defaultUserRolePermissions resource type

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Contains certains customizable permissions of default user role in Azure AD.

## Properties

| Property | Type | Description |
|:-------- |:---- |:----------- |
| allowedToCreateApps | Boolean | Indicates whether the default user role can create applications. |  
| allowedToCreateSecurityGroups | Boolean | Indicates whether the default user role can create security groups. |  
| allowedToReadBitlockerKeysForOwnedDevice | Boolean | Indicates whether the registered owners of a device can read their own BitLocker recovery keys with default user role. |
| allowedToReadOtherUsers | Boolean | Indicates whether the default user role can read other users. |  
| allowedToCreateTenants | Boolean | Indicates whether the default user role can create tenants. | 

## Relationships

None.

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.defaultUserRolePermissions"
}-->

```json
{
  "allowedToCreateApps": true,
  "allowedToCreateSecurityGroups": true,
  "allowedToReadBitlockerKeysForOwnedDevice": true,
  "allowedToReadOtherUsers": true,
  "allowedToCreateTenants": true
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "defaultUserRolePermissions resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


