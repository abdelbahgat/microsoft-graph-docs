---
title: printTaskStatus resource type
description: Represents the current execution status of a printTask.
author: nilakhan
ms.localizationpriority: medium
ms.prod: cloud-printing
doc_type: resourcePageType
---

# printTaskStatus resource type

Namespace: microsoft.graph

Represents the current execution status of a [printTask](printtask.md). 

## Properties
|Property|Type|Description|
|:---|:---|:---|
|description|String|A human-readable description of the current processing state of the [printTask](printtask.md).|
|state|printTaskProcessingState|The current processing state of the [printTask](printtask.md). Valid values are described in the following table.|

### printTaskProcessingState values

|Member|Value|Description|
|:---|:---|:---|
|pending|0|Task execution is pending.|
|processing|1|Task execution is in progress.|
|completed|2|Task execution has completed.|
|aborted|3|Task execution was aborted.|
|unknownFutureValue|4|Evolvable enumeration sentinel value. Do not use.|

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.printTaskStatus"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.printTaskStatus",
  "state": "String",
  "description": "String"
}
```

