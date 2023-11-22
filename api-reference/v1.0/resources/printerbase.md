---
title: printerBase resource type
description: Represents base type for printer and printer share
author: braedenp-msft
ms.localizationpriority: medium
ms.prod: cloud-printing
doc_type: resourcePageType
---
# printerBase resource type

Namespace: microsoft.graph

Represents a base type for [printer](printer.md) and [printerShare](printerShare.md) entity types.

## Properties
|Property|Type|Description|
|:---|:---|:---|
|capabilities|[printerCapabilities](printercapabilities.md)|The capabilities of the printer/printerShare.|
|defaults|[printerDefaults](printerdefaults.md)|The default print settings of printer/printerShare.|
|displayName|String|The name of the printer/printerShare.|
|id|String|The identifier.|
|isAcceptingJobs|Boolean|Specifies whether the printer/printerShare is currently accepting new print jobs.|
|location|[printerLocation](printerlocation.md)|The physical and/or organizational location of the printer/printerShare.|
|manufacturer|String|The manufacturer of the printer/printerShare.|
|model|String|The model name of the printer/printerShare.|
|status|[printerStatus](printerstatus.md)|The processing status of the printer/printerShare, including any errors.|

## Relationships
|Relationship|Type|Description|
|:---|:---|:---|
|jobs|[printJob](printjob.md) collection|The list of jobs that are queued for printing by the printer/printerShare.|

## JSON representation
Here's a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.printerBase",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.printerBase",
  "id": "String (identifier)",
  "displayName": "String",
  "manufacturer": "String",
  "model": "String",
  "isAcceptingJobs": "Boolean",
  "defaults": {
    "@odata.type": "microsoft.graph.printerDefaults"
  },
  "location": {
    "@odata.type": "microsoft.graph.printerLocation"
  },
  "capabilities": {
    "@odata.type": "microsoft.graph.printerCapabilities"
  },
  "status": {
    "@odata.type": "microsoft.graph.printerStatus"
  }
}
```

