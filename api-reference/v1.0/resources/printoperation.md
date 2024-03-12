---
title: printOperation resource type
description: Represents a long-running Universal Print operation. Base class for operation types such as printerCreateOperation.
author: nilakhan
ms.localizationpriority: medium
ms.prod: cloud-printing
doc_type: resourcePageType
---

# printOperation resource type

Namespace: microsoft.graph

Represents a long-running Universal Print operation. Base class for operation types such as [printerCreateOperation](printercreateoperation.md).

## Methods
|Method|Return type|Description|
|:---|:---|:---|
| [Get operation](../api/printoperation-get.md) | [printOperation](printoperation.md) | Retrieve a long-running operation within current user or app's tenant. |

## Properties
|Property|Type|Description|
|:---|:---|:---|
|createdDateTime|DateTimeOffset|The DateTimeOffset when the operation was created. Read-only.|
|id|String|The operation's identifier. Read-only.|
|status|[printOperationStatus](printoperationstatus.md)|The status of the operation. Read-only.|

## Relationships
None.

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.printOperation",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.printOperation",
  "id": "String (identifier)",
  "status": {
    "@odata.type": "microsoft.graph.printOperationStatus"
  },
  "createdDateTime": "String (timestamp)"
}
```

