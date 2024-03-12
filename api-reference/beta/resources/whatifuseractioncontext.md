---
title: "whatIfUserActionContext resource type"
description: "**TODO: Add Description**"
author: "**TODO: Provide GitHub Name. See [topic-level metadata reference](https://aka.ms/msgo?pagePath=Document-APIs/Guidelines/Metadata)**"
ms.localizationpriority: medium
ms.subservice: "**TODO: Add MS prod. See [topic-level metadata reference](https://aka.ms/msgo?pagePath=Document-APIs/Guidelines/Metadata)**"
doc_type: resourcePageType
---

# whatIfUserActionContext resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

**TODO: Add Description**


Inherits from [conditionalAccessContext](../resources/conditionalaccesscontext.md).

## Properties
|Property|Type|Description|
|:---|:---|:---|
|userAction|userAction|**TODO: Add Description**.The possible values are: `registerSecurityInformation`, `registerOrJoinDevices`, `unknownFutureValue`.|

## Relationships
None.

## JSON representation
The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.whatIfUserActionContext"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.whatIfUserActionContext",
  "userAction": "String"
}
```

