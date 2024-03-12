---
title: "unifiedRoleDefinition resource type"
description: "A unified role definition is a collection of permissions"
ms.localizationpriority: medium
author: "DougKirschner"
ms.prod: "directory-management"
doc_type: "resourcePageType"
---

# unifiedRoleDefinition resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a collection of permissions listing the operations, such as read, write, and delete, that can be performed by an RBAC provider, as part of Microsoft 365 RBAC [role management](rolemanagement.md).

The following RBAC providers are currently supported:
- Cloud PC 
- device management (Intune)
- directory (Azure AD) 
- entitlement management (Azure AD)
- Exchange Online


## Methods

| Method       | Return Type | Description |
|:-------------|:------------|:------------|
| [List roleDefinitions](../api/rbacapplication-list-roledefinitions.md) | [unifiedRoleDefinition](unifiedroledefinition.md) collection | Read a list of unifiedRoleDefinition objects, and their properties. |
| [Get unifiedRoleDefinition](../api/unifiedroledefinition-get.md) | [unifiedRoleDefinition](unifiedroledefinition.md) | Read the properties of a unifiedRoleDefinition object. |
| [Create roleDefinitions](../api/rbacapplication-post-roledefinitions.md) | [unifiedRoleDefinition](unifiedroledefinition.md) | Create a unifiedRoleDefinition object. |
| [Update unifiedRoleDefinition](../api/unifiedroledefinition-update.md) | [unifiedRoleDefinition](unifiedroledefinition.md) | Update a unifiedRoleDefinition object. |
| [Delete unifiedRoleDefinition](../api/unifiedroledefinition-delete.md) | None | Delete a unifiedRoleDefinition object. |
| [List assignedPrincipals](../api/unifiedroledefinition-assignedprincipals.md) | [directoryObject](../resources/directoryobject.md) collection|Get the users and groups assigned to a role across all scopes.|

## Properties

| Property     | Type        | Description |
|:-------------|:------------|:------------|
|description|String| The description for the unifiedRoleDefinition. Read-only when **isBuiltIn** is true. |
|displayName|String| The display name for the unifiedRoleDefinition. Read-only when **isBuiltIn** is true. Required.  Supports `$filter` (`eq` and `startsWith` operators only).|
|id|String| The unique identifier for the unifiedRoleDefinition. Key, not nullable, Read-only.  Supports `$filter` (`eq` operator only). |
|isBuiltIn|Boolean| Flag indicating if the unifiedRoleDefinition is part of the default set included with the product or custom. Read-only.  Supports `$filter` (`eq` operator only).|
|isEnabled|Boolean| Flag indicating if the role is enabled for assignment. If false the role is not available for assignment. Read-only when **isBuiltIn** is true. |
|resourceScopes|String collection| List of scopes permissions granted by the role definition apply to. Currently only `/` is supported. Read-only when isBuiltIn is true. **DO NOT USE. This will be deprecated soon. Attach scope to role assignment** | 
|rolePermissions|[unifiedRolePermission](unifiedrolepermission.md) collection| List of permissions included in the role. Read-only when **isBuiltIn** is true. Required. |
|templateId|String| Custom template identifier that can be set when isBuiltIn is false. This identifier is typically used if one needs an identifier to be the same across different directories. Read-only when **isBuiltIn** is true. |
|version|String| Indicates version of the unifiedRoleDefinition. Read-only when **isBuiltIn** is true.|

## Relationships

| Relationship | Type	|Description|
|:---------------|:--------|:----------|
|inheritsPermissionsFrom| [unifiedRoleDefinition](unifiedroledefinition.md) collection| Read-only collection of role definitions that the given role definition inherits from. Only Azure AD built-in roles support this attribute. |

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.unifiedRoleDefinition",
  "keyProperty": "id"
}-->

```json
{
  "description": "String",
  "displayName": "String",
  "id": "String (identifier)",
  "isBuiltIn": true,
  "isEnabled": true,
  "resourceScopes": ["String"],
  "rolePermissions": [{"@odata.type": "microsoft.graph.unifiedRolePermission"}],
  "templateId": "String",
  "inheritsPermissionsFrom": [{"@odata.type": "microsoft.graph.unifiedRoleDefinition"}],
  "version": "String"
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "unifiedRoleDefinition resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->


