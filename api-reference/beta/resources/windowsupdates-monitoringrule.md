---
title: "monitoringRule resource type"
description: "Rule defining a signal and threshold to monitor, and the action to perform when met."
author: "ryan-k-williams"
ms.localizationpriority: medium
ms.prod: "w10"
doc_type: resourcePageType
---

# monitoringRule resource type

Namespace: microsoft.graph.windowsUpdates

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Rule defining a signal and threshold to monitor, and the action to perform when met.

## Properties
|Property|Type|Description|
|:---|:---|:---|
|action|microsoft.graph.windowsUpdates.monitoringAction|	The action triggered when the threshold for the given signal is met. Possible values are: `alertError`, `pauseDeployment`, `unknownFutureValue`.|
|signal|microsoft.graph.windowsUpdates.monitoringSignal|The signal to monitor. Possible values are: `rollback`, `unknownFutureValue`.|
|threshold|Int32|The threshold for a signal at which to trigger action. An integer from 1 to 100 (inclusive).|

## Relationships
None.

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.windowsUpdates.monitoringRule"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.windowsUpdates.monitoringRule",
  "signal": "String",
  "threshold": "Integer",
  "action": "String"
}
```

