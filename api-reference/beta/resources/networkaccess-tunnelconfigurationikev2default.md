---
title: "tunnelConfigurationIKEv2Default resource type"
description: "Specifies connectivity settings such as protocol, IPSec policy, and preshared key) for establishing connectivity."
author: "Moti-ba"
ms.localizationpriority: medium
ms.prod: global-secure-access
doc_type: resourcePageType
---

# tunnelConfigurationIKEv2Default resource type

Namespace: microsoft.graph.networkaccess

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Specifies connectivity settings such as protocol, IPSec policy, and preshared key) for establishing connectivity.

Inherits from [microsoft.graph.networkaccess.tunnelConfiguration](../resources/networkaccess-tunnelconfiguration.md).

## Properties
|Property|Type|Description|
|:---|:---|:---|
|preSharedKey|String|A key to establish secure connection between the link and VPN tunnel on the edge. Inherited from [microsoft.graph.networkaccess.tunnelConfiguration](../resources/networkaccess-tunnelconfiguration.md).|

## Relationships
None.

## JSON representation
Here's a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.networkaccess.tunnelConfigurationIKEv2Default"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.networkaccess.tunnelConfigurationIKEv2Default",
  "preSharedKey": "String"
}
```

