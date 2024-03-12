---
title: "complianceInformation resource type"
description: "This resource contains compliance data associated with secure score control."
ms.localizationpriority: medium
author: preetikr
ms.prod: security
doc_type: resourcePageType
---

#  complianceInformation resource type

Namespace: microsoft.graph

Contains compliance data associated with secure score control.

## Properties

|Property |Type |Description |
|:--|:--|:--|
|certificationControls|[certificationControl](certificationcontrol.md) collection|Collection of the certification controls associated with certification|
|certificationName|String| Compliance certification name (for example, ISO 27018:2014, GDPR, FedRAMP, NIST 800-171) |

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.complianceInformation"
}-->

```json
{
  "certificationControls": [{"@odata.type": "microsoft.graph.certificationControl"}],
  "certificationName": "String"
}

```


<!-- {
  "type": "#page.annotation",
  "description": "complianceInformation resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

