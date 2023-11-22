---
title: "positionDetail resource type"
description: "positionDetail resource type"
ms.localizationpriority: medium
author: "kevinbellinger"
ms.prod: "people"
doc_type: "resourcePageType"
---

# positionDetail resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents information about positions related to entities within a user's [profile](profile.md).

## Properties

| Property       | Type                             | Description                                                           |
|:---------------|:---------------------------------|:----------------------------------------------------------------------|
|company         |[companyDetail](companydetail.md) | Detail about the company or employer.                                 |
|description     |String                            | Description of the position in question.                              |
|endMonthYear    |Date                              | When the position ended.                                              |
|jobTitle        |String                            | The title held when in that position.                                 |
|layer           |Int32                             | The place where the employee is within the organizational hierarchy.      |
|level           |String                            | The employee’s experience or management level.                        |
|role            |String                            | The role the position entailed.                                       |
|startMonthYear  |Date                              | The start month and year of the position.                             |
|summary         |String                            | summary of the position.                                         |

## JSON representation

The following JSON representation shows the resource type.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.positionDetail",
  "baseType": null
}-->

```json
{
  "company": {"@odata.type": "microsoft.graph.companyDetail"},
  "description": "String",
  "endMonthYear": "String (timestamp)",
  "jobTitle": "String",
  "layer": "Integer",
  "level": "String",
  "role": "String",
  "startMonthYear": "String (timestamp)",
  "summary": "String"
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "positionDetail resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

