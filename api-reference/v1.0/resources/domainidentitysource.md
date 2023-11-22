---
title: "domainIdentitySource resource type"
description: "The domainIdentitySource type identifies a non-tenant domain as an identity source for a connected organization."
author: "markwahl-msft"
ms.localizationpriority: medium
ms.prod: "governance"
doc_type: resourcePageType
---
# domainIdentitySource resource type

Namespace: microsoft.graph


Used in the identity sources of an [connectedOrganization](connectedOrganization.md). The `@odata.type` value `#microsoft.graph.domainIdentitySource` indicates that this type identifies a domain as an identity source for a connected organization.

When you're [creating a new connectedOrganization](../api/entitlementmanagement-post-connectedorganizations.md), if the caller provides in the identitySources collection a domainIdentitySource and the domain corresponds to a registered domain of a Microsoft Entra tenant, then the resulting connectedOrganization that is created has an identitySources collection containing a single member of the [azureActiveDirectoryTenant](azureactivedirectorytenant.md) type.

## Properties
|Property|Type|Description|
|:---|:---|:---|
|displayName|String|The name of the identity source, typically also the domain name. Read only. |
|domainName|String|The domain name. Read only. |

## Relationships
None.
## JSON representation
Here's a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.domainIdentitySource",
  "baseType": "microsoft.graph.identitySource"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.domainIdentitySource",
  "displayName": "String",
  "domainName": "String"
}
```
