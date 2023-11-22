---
title: "onPremisesPublishingProfile resource type"
description: "onPremisesPublishingProfile resource type."
ms.localizationpriority: medium
author: "dhruvinrshah"
ms.prod: "applications"
doc_type: "resourcePageType"
---

# onPremisesPublishingProfile resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Various Azure services (for example, Microsoft Entra Connect [Passthrough Authentication](/azure/active-directory/hybrid/how-to-connect-pta), [Workday to Microsoft Entra users provisioning](/azure/active-directory/saas-apps/workday-inbound-tutorial), and [Application Proxy](/azure/active-directory/app-proxy/what-is-application-proxy) allow access to various on-premises resources from outside the corporate network.

[On-premises agents](onpremisesagent.md) (or [connectors](connector.md) for Application Proxy) installed by an administrator can be configured to route requests to a particular [published resource](publishedresource.md).
[Agent groups](onpremisesagentgroup.md) (or [connector groups](connectorgroup.md) for Application Proxy) enable an administrator to assign specific agents to serve specific published on-premises resources. Administrators can also group multiple agents together, and then assign each published resource to an agent group. The entire set of entities of the same on-premises publishing type is represented by **onPremisesPublishingProfile**.

## Methods

| Method       | Return Type | Description |
|:-------------|:------------|:------------|
| [Get onPremisesPublishingProfile](../api/onpremisespublishingprofile-get.md) | [onPremisesPublishingProfile](onpremisespublishingprofile.md) | Read the properties and relationships of an **onPremisesPublishingProfile** object. |
| [Update onPremisesPublishingProfile](../api/onpremisespublishingprofile-update.md) | None | Update an [onPremisesPublishingProfile](onpremisespublishingprofile.md) object. |

## Properties

| Property     | Type        | Description |
|:-------------|:------------|:------------|
|hybridAgentUpdaterConfiguration|[hybridAgentUpdaterConfiguration](hybridagentupdaterconfiguration.md)| Represents a **hybridAgentUpdaterConfiguration** object.|
|id|String| Represents a publishing type. Possible values are: `applicationProxy`, `exchangeOnline`, `authentication`, `provisioning`, `adAdministration`. Read-only.|
|isEnabled|Boolean| Represents if [Microsoft Entra application proxy](/azure/active-directory/app-proxy/what-is-application-proxy) is enabled for the tenant. |

## Relationships

| Relationship | Type        | Description |
|:-------------|:------------|:------------|
|agentGroups|[onPremisesAgentGroup](onpremisesagentgroup.md) collection| List of existing **onPremisesAgentGroup** objects. Read-only. Nullable.|
|agents|[onPremisesAgent](onpremisesagent.md) collection| List of existing **onPremisesAgent** objects. Read-only. Nullable.|
|connectorGroups|[connectorGroup](connectorgroup.md) collection| List of existing **connectorGroup** objects for applications published through Application Proxy. Read-only. Nullable.|
|connectors|[connector](connector.md) collection| List of existing **connector** objects for applications published through Application Proxy. Read-only. Nullable.|
|publishedResources|[publishedResource](publishedresource.md) collection| List of existing **publishedResource** objects. Read-only. Nullable.|

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.onPremisesPublishingProfile",
  "keyProperty": "id"
}-->

```json
{
  "hybridAgentUpdaterConfiguration": {"@odata.type": "microsoft.graph.hybridAgentUpdaterConfiguration"},
  "id": "String (identifier)"
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "onPremisesPublishingProfile resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
