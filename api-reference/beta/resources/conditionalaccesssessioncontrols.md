---
title: "conditionalAccessSessionControls resource type"
description: "Represents a complex type of session controls that is enforced after sign-in."
ms.localizationpriority: medium
author: "lisaychuang"
ms.reviewer: conditionalaccesspm
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
---

# conditionalAccessSessionControls resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents session controls that are enforced after sign-in.
All the session controls inherit from [conditionalAccessSessionControl](conditionalaccesssessioncontrol.md).

## Properties

| Property     | Type        | Description |
|:-------------|:------------|:------------|
|applicationEnforcedRestrictions|[applicationEnforcedRestrictionsSessionControl](applicationenforcedrestrictionssessioncontrol.md)| Session control to enforce application restrictions. Only Exchange Online and Sharepoint Online support this session control. |
|cloudAppSecurity|[cloudAppSecuritySessionControl](cloudappsecuritysessioncontrol.md)| Session control to apply cloud app security.|
|continuousAccessEvaluation|[continuousAccessEvaluationSessionControl](../resources/continuousaccessevaluationsessioncontrol.md)|Session control for continuous access evaluation settings.|
|disableResilienceDefaults|Boolean| Session control that determines whether it's acceptable for Microsoft Entra ID to extend existing sessions based on information collected prior to an outage or not.|
|persistentBrowser|[persistentBrowserSessionControl](persistentbrowsersessioncontrol.md)| Session control to define whether to persist cookies or not. All apps should be selected for this session control to work correctly. |
|secureSignInSession|[secureSignInSessionControl](securesigninsessioncontrol.md)|Session control to require sign in sessions to be bound to a device.|
|signInFrequency|[signInFrequencySessionControl](signinfrequencysessioncontrol.md)| Session control to enforce signin frequency.|

## Relationships

None.

## JSON representation

Here's a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [
    "applicationEnforcedRestrictions",
    "cloudAppSecurity",
    "continuousAccessEvaluation",
    "disableResilienceDefaults",
    "persistentBrowser",
    "signInFrequency"
  ],
  "@odata.type": "microsoft.graph.conditionalAccessSessionControls",
  "baseType": null
}-->

```json
{
  "applicationEnforcedRestrictions": {"@odata.type": "microsoft.graph.applicationEnforcedRestrictionsSessionControl"},
  "cloudAppSecurity": {"@odata.type": "microsoft.graph.cloudAppSecuritySessionControl"},
  "continuousAccessEvaluation": {"@odata.type": "microsoft.graph.continuousAccessEvaluationSessionControl"},
  "persistentBrowser": {"@odata.type": "microsoft.graph.persistentBrowserSessionControl"},
  "signInFrequency": {"@odata.type": "microsoft.graph.signInFrequencySessionControl"},
  "disableResilienceDefaults": false,
  "secureSignInSession": {"@odata.type": "microsoft.graph.secureSignInSessionControl"},
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "conditionalAccessSessionControls resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
