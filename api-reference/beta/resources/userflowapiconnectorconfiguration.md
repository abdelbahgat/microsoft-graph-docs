---
title: "userFlowApiConnectorConfiguration resource type"
description: "Represents which API connectors are enabled for a user flow."
author: "nickgmicrosoft"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
---

# userFlowApiConnectorConfiguration resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Defines which APIs are called at specific points in the user flow.  Each relationship of this object corresponds to a specific step in the user flow that can be configured to call an API connector.

## Relationships

| Relationship            | Type                                            | Description                                                                                                                                             |
| :---------------------- | :---------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------ |
| postFederationSignup    | [identityApiConnector](identityapiconnector.md) | Specifies an API to call after federation with an external identity provider (like Google, Facebook, or Microsoft Entra ID) is completed when user is signing up (doesn't apply to sign in). |
| postAttributeCollection | [identityApiConnector](identityapiconnector.md) | Specifies an API to call after a user submits collected attributes and before the user is created during sign-up.                                                      |

## JSON representation

Here's a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.userFlowApiConnectorConfiguration"
}
-->

``` json
{
  "@odata.type": "#microsoft.graph.userFlowApiConnectorConfiguration"
}
```

<!-- {
  "type": "#page.annotation",
  "description": "User flow API Connector Configuration",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}-->
