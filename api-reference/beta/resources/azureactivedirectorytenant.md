---
title: "azureActiveDirectoryTenant resource type"
description: "The azureActiveDirectoryTenant type identifies another Microsoft Entra tenant as an identity source for a connected organization."
ms.localizationpriority: medium
author: "markwahl-msft"
ms.prod: "governance"
doc_type: "resourcePageType"
---

# azureActiveDirectoryTenant resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Used in the identity sources of an [connectedOrganization](connectedOrganization.md). The `@odata.type` value `#microsoft.graph.azureActiveDirectoryTenant` indicates that this type identifies another Microsoft Entra tenant as an identity source for a connected organization.

When [creating a new connectedOrganization](../api/entitlementmanagement-post-connectedorganizations.md), if the caller provides in the identitySources collection a domainIdentitySource and the domain corresponds to a registered domain of a Microsoft Entra tenant, then the resulting connectedOrganization that is created will have an identitySources collection containing a single member of the [azureActiveDirectoryTenant](azureactivedirectorytenant.md) type.

## Properties

| Property                     | Type                      | Description |
| :--------------------------- | :------------------------ | :---------- |
| displayName |String | The name of the Microsoft Entra tenant. Read only. |
| tenantId |String | The ID of the Microsoft Entra tenant. Read only. |

## Relationships

None.

## JSON representation

The following is a JSON representation of the type.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.azureActiveDirectoryTenant",
  "baseType": "microsoft.graph.identitySource"
}-->

```json
{
  "tenantId": "String (identifier)",
  "displayName": "String"
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "azureActiveDirectoryTenant resource type",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
