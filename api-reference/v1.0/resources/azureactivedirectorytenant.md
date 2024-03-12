---
title: "azureActiveDirectoryTenant resource type"
description: "The azureActiveDirectoryTenant type identifies another Azure Active Directory tenant as an identity source for a connected organization."
author: "markwahl-msft"
ms.localizationpriority: medium
ms.prod: "governance"
doc_type: resourcePageType
---
# azureActiveDirectoryTenant resource type

Namespace: microsoft.graph


Used in the identity sources of an [connectedOrganization](connectedOrganization.md). The `@odata.type` value `#microsoft.graph.azureActiveDirectoryTenant` indicates that this type identifies another Azure Active Directory tenant as an identity source for a connected organization.

When [creating a new connectedOrganization](../api/entitlementmanagement-post-connectedorganizations.md), if the caller provides in the identitySources collection a domainIdentitySource and the domain corresponds to a registered domain of an Azure Active Directory tenant, then the resulting connectedOrganization that is created will have an identitySources collection containing a single member of the [azureActiveDirectoryTenant](azureactivedirectorytenant.md) type.

## Properties
|Property|Type|Description|
|:---|:---|:---|
|displayName|String|The name of the Azure Active Directory tenant. Read only. |
|tenantId|String|The ID of the Azure Active Directory tenant. Read only. |

## Relationships
None.
## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.azureActiveDirectoryTenant",
  "baseType": "microsoft.graph.identitySource"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.azureActiveDirectoryTenant",
  "displayName": "String",
  "tenantId": "String"
}
```



