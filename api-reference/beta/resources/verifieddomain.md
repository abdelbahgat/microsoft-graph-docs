---
title: "verifiedDomain resource type"
description: "Specifies a domain for a tenant. The verifiedDomains property of the organization entity is a collection of verifiedDomain objects."
ms.localizationpriority: medium
doc_type: resourcePageType
ms.prod: "directory-management"
author: "Jumaodhiss"
---

# verifiedDomain resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Specifies a domain for a tenant. The **verifiedDomains** property of the [organization](organization.md) entity is a collection of **verifiedDomain** objects.


## Properties
| Property     | Type    | Description                                                                          |
|:-------------|:--------|:-------------------------------------------------------------------------------------|
| capabilities | String  | For example, `Email`, `OfficeCommunicationsOnline`.                                  |
| isDefault    | Boolean | `true` if this is the default domain associated with the tenant; otherwise, `false`. |
| isInitial    | Boolean | `true` if this is the initial domain associated with the tenant; otherwise, `false`. |
| name         | String  | The domain name; for example, `contoso.onmicrosoft.com`.                             |
| type         | String  | For example, `Managed`.                                                              |

## JSON representation

Here is a JSON representation of the resource

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.verifiedDomain"
}-->

```json
{
  "capabilities": "String",
  "isDefault": true,
  "isInitial": true,
  "name": "String",
  "type": "String"
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "verifiedDomain resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


