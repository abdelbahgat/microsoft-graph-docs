---
title: "externalItem resource type"
description: "An item added to a Microsoft Graph connection."
author: "mecampos"
ms.localizationpriority: medium
ms.prod: "search"
doc_type: resourcePageType
---

# externalItem resource type

Namespace: microsoft.graph.externalConnectors

An item added to a Microsoft Graph [connection](externalconnectors-externalconnection.md).

## Methods
|Method|Return type|Description|
|:---|:---|:---|
| [Create externalItem](../api/externalconnectors-externalconnection-put-items.md)  | [externalItem](../resources/externalconnectors-externalitem.md)  | Create a new [externalItem](../resources/externalconnectors-externalitem.md) object.|
| [Get externalItem](../api/externalconnectors-externalitem-get.md)        | [externalItem](../resources/externalconnectors-externalitem.md)|Read the properties and relationships of an [externalItem](../resources/externalconnectors-externalitem.md) object.|
| [Update externalItem](../api/externalconnectors-externalitem-update.md)  | [externalItem](../resources/externalconnectors-externalitem.md)|Update the properties of an [externalItem](../resources/externalconnectors-externalitem.md) object.|
| [Delete externalItem](../api/externalconnectors-externalitem-delete.md)  | None |Delete an [externalItem](../resources/externalconnectors-externalitem.md) object.|
| [Add activities](../api/externalconnectors-externalitem-addactivities.md) | [microsoft.graph.externalConnectors.externalActivityResult](../resources/externalconnectors-externalactivity.md) collection | Append additional instances of [externalActivity](../resources/externalconnectors-externalactivity.md) objects on an **externalItem**.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
|acl|[microsoft.graph.externalConnectors.acl](../resources/externalconnectors-acl.md) collection|An array of access control entries. Each entry specifies the access granted to a user or group. Required.|
|content|[microsoft.graph.externalConnectors.externalItemContent](../resources/externalconnectors-externalitemcontent.md)|A plain-text  representation of the contents of the item. The text in this property is full-text indexed. Optional.|
|id|String|Developer-provided unique ID of the item within the containing [externalConnection](externalconnectors-externalconnection.md). Must be alphanumeric and a maximum of 128 characters. Required.|
|properties|[microsoft.graph.externalConnectors.properties](../resources/externalconnectors-properties.md)|A property bag with the properties of the item. The properties MUST conform to the [schema](externalconnectors-schema.md) defined for the [externalConnection](externalconnectors-externalconnection.md). Required.|

## Relationships

| Relationship | Type                                                     | Description |
|:-------------|:---------------------------------------------------------|:---|
| activities        | [microsoft.graph.externalConnectors.externalActivity](externalconnectors-externalactivity.md) collection               | Returns a list of activities performed on the item. Write-only. |

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.externalConnectors.externalItem",
  "openType": false
}
-->
```json
{
  "acl": [
    {
      "type": "everyone",
      "value": "67a141d8-cf4e-4528-ba07-bed21bfacd2d",
      "accessType": "grant"
    }
  ],
  "content": {
    "@odata.type": "microsoft.graph.externalConnectors.externalItemContent"
  },
  "id": "String (identifier)",
  "properties": {
    "@odata.type": "microsoft.graph.externalConnectors.properties"
  }
}
```

