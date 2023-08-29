---
title: "addContentHeaderAction resource type"
description: "Represents an action that specifies the details on the content header to be added to the information, if applicable."
ms.localizationpriority: medium
author: "tommoser"
ms.prod: "security"
doc_type: "resourcePageType"
---

# addContentHeaderAction resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents an action that specifies the details on the content header to be added to the information, if applicable.

## Properties

| Property      | Type   | Description                                                   |
| :------------ | :----- | :------------------------------------------------------------ |
| alignment     | String | Possible values are: `left`, `right`, `center`.               |
| fontColor     | String | Color of the font to use for the header.                      |
| fontName      | String | Name of the font to use for the header.                       |
| fontSize      | Int32  | Font size to use for the header.                              |
| margin        | Int32  | The margin of the header from the top of the document.        |
| text          | String | The contents of the header itself.                            |
| uiElementName | String | The name of the UI element where the header should be placed. |

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.addContentHeaderAction",
  "baseType": "microsoft.graph.informationProtectionAction"
}-->

```json
{
  "alignment": "String",
  "fontColor": "String",
  "fontName": "String",
  "fontSize": 1024,
  "margin": 1024,
  "text": "String",
  "uiElementName": "String"
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "addContentHeaderAction resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

