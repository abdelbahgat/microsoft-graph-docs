---
title: "unifiedRoleAssignment resource type"
description: "A role assignment is the link between a role definition and a principal at a particular scope for the purpose of granting access."
ms.localizationpriority: medium
author: "abhijeetsinha"
ms.prod: "directory-management"
doc_type: "resourcePageType"
---

# unifiedRoleAssignment resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

A unifiedRoleAssignment is used to grant access to resources. It represents a role definition assigned to a principal (typically a user) at a particular scope.

Providing either a directoryScopeId or an appScopeId is required.

## Methods

| Method       | Return Type | Description |
|:-------------|:------------|:------------|
| [List unifiedRoleAssignment](../api/rbacapplication-list-roleassignments.md) | [unifiedRoleAssignment](unifiedroleassignment.md) | Read a list of unifiedRoleAssignment objects and their properties. |
| [List transitiveRoleAssignments](../api/rbacapplication-list-transitiveroleassignments.md) | [unifiedRoleAssignment](unifiedroleassignment.md) collection | Get direct and transitive unifiedRoleAssignments assigned to a specific principal. Specifying principalId is required. |
| [Get unifiedRoleAssignment](../api/unifiedroleassignment-get.md) | [unifiedRoleAssignment](unifiedroleassignment.md) | Read properties and relationships of unifiedRoleAssignment object. |
| [Create unifiedRoleAssignment](../api/rbacapplication-post-roleassignments.md) | [unifiedRoleAssignment](unifiedroleassignment.md) | Create a new unifiedRoleAssignment by posting to the roleAssignment collection. |
| [Delete unifiedRoleAssignment](../api/unifiedroleassignment-delete.md) | None | Delete unifiedRoleAssignment object. |

## Properties

| Property     | Type        | Description |
|:-------------|:------------|:------------|
|id|String| The unique identifier for the unifiedRoleAssignment. Key, not nullable, Read-only. |
|roleDefinitionId|String| Identifier of the unifiedRoleDefinition the assignment is for. Read-only. Supports `$filter` (`eq` operator only). |
|principalId|String| Identifier of the principal to which the assignment is granted. Supports `$filter` (`eq` operator only). |
|directoryScopeId|String|Identifier of the directory object representing the scope of the assignment. The scope of an assignment determines the set of resources for which the principal has been granted access. Directory scopes are shared scopes stored in the directory that are understood by multiple applications. App scopes are scopes that are defined and understood by this application only.|
|appScopeId|String|Identifier of the app specific scope when the assignment scope is app specific. The scope of an assignment determines the set of resources for which the principal has been granted access. Directory scopes are shared scopes stored in the directory that are understood by multiple applications. Use `/` for tenant-wide scope. App scopes are scopes that are defined and understood by this application only.  For the entitlement management provider, use app scopes to specify a catalog, for example `/AccessPackageCatalog/beedadfe-01d5-4025-910b-84abb9369997`.|
|resourceScope|String| The scope at which the unifiedRoleAssignment applies. This is `/` for service-wide. **DO NOT USE. This property will be deprecated soon.**|

## Relationships

| Relationship | Type	|Description|
|:---------------|:--------|:----------|
|appScope|[appScope](appscope.md)|Details of the app specific scope when the assignment scope is app specific. Containment entity. |
|directoryScope|[directoryObject](directoryobject.md)|The directory object that is the scope of the assignment. Provided so that callers can get the directory object using `$expand` at the same time as getting the role assignment. Read-only. Supports `$expand`. |
|principal|[directoryObject](directoryobject.md)| The assigned principal. Provided so that callers can get the principal using `$expand` at the same time as getting the role assignment. Read-only. Supports `$expand`. |
|roleDefinition|[unifiedRoleDefinition](unifiedroledefinition.md)|The roleDefinition the assignment is for. Provided so that callers can get the role definition using `$expand` at the same time as getting the role assignment. **roleDefinition.id** will be auto expanded. Supports `$expand`. |



## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.unifiedRoleAssignment",
  "keyProperty": "id"
}-->

```json
{
  "id": "String (identifier)",
  "roleDefinitionId": "String",
  "roleDefinition": {"@odata.type": "microsoft.graph.unifiedRoleDefinition"},
  "principalId": "String",
  "principal": {"@odata.type": "microsoft.graph.directoryObject"},
  "directoryScopeId": "String",
  "directoryScope": {"@odata.type": "microsoft.graph.directoryObject"},
  "appScopeId": "String",
  "appScope": {"@odata.type": "microsoft.graph.appScope"},
  "resourceScope": "String"
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "unifiedRoleAssignment resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
