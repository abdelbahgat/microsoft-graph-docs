---
title: "provisioningStatusInfo resource type"
description: "Describes the status of the provisioning summary event."
ms.localizationpriority: medium
author: "ArvindHarinder1"
ms.prod: "governance"
doc_type: "resourcePageType"
---

# provisioningStatusInfo resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Describes the status of the provisioning summary event. 

## Properties

| Property     | Type        | Description |
|:-------------|:------------|:------------|
|status|provisioningResult| Possible values are: `success`, `failure`, `skipped`, `warning`, `unknownFutureValue`. Supports `$filter` (`eq`, `contains`).|
|errorInformation|[provisioningErrorInfo](provisioningerrorinfo.md)| If status isn't success/ skipped details for the error are contained in this.|

## JSON representation

Here's a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.provisioningStatusInfo",
  "baseType": null
}-->

```json
{
  "status": "String",
  "errorInformation": {
    "@odata.type": "microsoft.graph.provisioningErrorInfo"
  }
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "provisioningStatusInfo resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->


