---
title: "conditionalAccessWhatIfPolicy resource type"
description: "**TODO: Add Description**"
author: "**TODO: Provide GitHub Name. See [topic-level metadata reference](https://aka.ms/msgo?pagePath=Document-APIs/Guidelines/Metadata)**"
ms.localizationpriority: medium
ms.subservice: "**TODO: Add MS prod. See [topic-level metadata reference](https://aka.ms/msgo?pagePath=Document-APIs/Guidelines/Metadata)**"
doc_type: resourcePageType
---

# conditionalAccessWhatIfPolicy resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

**TODO: Add Description**


Inherits from [conditionalAccessPolicy](../resources/conditionalaccesspolicy.md).

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[List conditionalAccessWhatIfPolicy objects](../api/conditionalaccesswhatifpolicy-list.md)|[conditionalAccessWhatIfPolicy](../resources/conditionalaccesswhatifpolicy.md) collection|Get a list of the [conditionalAccessWhatIfPolicy](../resources/conditionalaccesswhatifpolicy.md) objects and their properties.|
|[Get conditionalAccessWhatIfPolicy](../api/conditionalaccesswhatifpolicy-get.md)|[conditionalAccessWhatIfPolicy](../resources/conditionalaccesswhatifpolicy.md)|Read the properties and relationships of a [conditionalAccessWhatIfPolicy](../resources/conditionalaccesswhatifpolicy.md) object.|
|[Update conditionalAccessWhatIfPolicy](../api/conditionalaccesswhatifpolicy-update.md)|[conditionalAccessWhatIfPolicy](../resources/conditionalaccesswhatifpolicy.md)|Update the properties of a [conditionalAccessWhatIfPolicy](../resources/conditionalaccesswhatifpolicy.md) object.|
|[Delete conditionalAccessWhatIfPolicy](../api/conditionalaccesswhatifpolicy-delete.md)|None|Delete a [conditionalAccessWhatIfPolicy](../resources/conditionalaccesswhatifpolicy.md) object.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
|conditions|[conditionalAccessConditionSet](../resources/conditionalaccessconditionset.md)|**TODO: Add Description** Inherited from [conditionalAccessPolicy](../resources/conditionalaccesspolicy.md).|
|createdDateTime|DateTimeOffset|**TODO: Add Description** Inherited from [conditionalAccessPolicy](../resources/conditionalaccesspolicy.md).|
|description|String|**TODO: Add Description** Inherited from [conditionalAccessPolicy](../resources/conditionalaccesspolicy.md).|
|displayName|String|**TODO: Add Description** Inherited from [conditionalAccessPolicy](../resources/conditionalaccesspolicy.md).|
|grantControls|[conditionalAccessGrantControls](../resources/conditionalaccessgrantcontrols.md)|**TODO: Add Description** Inherited from [conditionalAccessPolicy](../resources/conditionalaccesspolicy.md).|
|id|String|**TODO: Add Description** Inherited from [entity](../resources/entity.md).|
|modifiedDateTime|DateTimeOffset|**TODO: Add Description** Inherited from [conditionalAccessPolicy](../resources/conditionalaccesspolicy.md).|
|policyApplies|Boolean|**TODO: Add Description**|
|reasons|conditionalAccessWhatIfReasons collection|**TODO: Add Description**|
|sessionControls|[conditionalAccessSessionControls](../resources/conditionalaccesssessioncontrols.md)|**TODO: Add Description** Inherited from [conditionalAccessPolicy](../resources/conditionalaccesspolicy.md).|
|state|conditionalAccessPolicyState|**TODO: Add Description** Inherited from [conditionalAccessPolicy](../resources/conditionalaccesspolicy.md).The possible values are: `enabled`, `disabled`, `enabledForReportingButNotEnforced`.|

## Relationships
None.

## JSON representation
The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.conditionalAccessWhatIfPolicy",
  "baseType": "microsoft.graph.conditionalAccessPolicy",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.conditionalAccessWhatIfPolicy",
  "id": "String (identifier)",
  "createdDateTime": "String (timestamp)",
  "modifiedDateTime": "String (timestamp)",
  "displayName": "String",
  "description": "String",
  "state": "String",
  "conditions": {
    "@odata.type": "microsoft.graph.conditionalAccessConditionSet"
  },
  "grantControls": {
    "@odata.type": "microsoft.graph.conditionalAccessGrantControls"
  },
  "sessionControls": {
    "@odata.type": "microsoft.graph.conditionalAccessSessionControls"
  },
  "policyApplies": "Boolean",
  "reasons": [
    "String"
  ]
}
```

