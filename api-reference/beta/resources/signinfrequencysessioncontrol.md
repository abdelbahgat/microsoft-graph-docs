---
title: "signInFrequencySessionControl resource type"
description: "Session control to enforce signin frequency."
ms.localizationpriority: medium
author: "rckyplln"
ms.prod: "identity-and-access-reports"
doc_type: resourcePageType
---

# signInFrequencySessionControl resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Session control to enforce sign-in frequency. Inherits from [Conditional Access Session Control](conditionalaccesssessioncontrol.md).

## Properties

| Property     | Type        | Description |
|:-------------|:------------|:------------|
|isEnabled     |Boolean      | Specifies whether the session control is enabled. |
|type          |signinFrequencyType       | Possible values are: `days`, `hours`, or `null` if frequencyInterval is `everyTime` .|
|value         |Int32        | The number of `days` or `hours`.|
|authenticationType |signInFrequencyAuthenticationType  | The possible values are `primaryAndSecondaryAuthentication`, `secondaryAuthentication`, `unknownFutureValue`.|
|frequencyInterval  |signInFrequencyInterval  | The possible values are `timeBased`, `everyTime`, `unknownFutureValue`.|

## Relationships

None.

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.signInFrequencySessionControl",
  "baseType": "microsoft.graph.conditionalAccessSessionControl"
}-->

```json
{
  "isEnabled":true,
  "type": "String",
  "value": 1024,
  "authenticationType": "String",
  "frequencyInterval": "String"
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "signInFrequencySessionControl resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->


