---
title: "teamsAppDefinition resource type"
description: "Represents the details of one version of a teamsApp."
author: "nkramer"
ms.localizationpriority: medium
ms.prod: "microsoft-teams"
doc_type: resourcePageType
---

# teamsAppDefinition resource type

Namespace: microsoft.graph

Represents the details of a version of a [teamsApp](teamsapp.md).

## Properties

| Property            | Type     | Description |
|:------------------- |:-------- |:----------- |
| id                  | string   | A unique ID (not the Teams app ID). |
| teamsAppId          | string   | The ID from the Teams app manifest. |
| publishingState| string|The published status of a specific version of a Teams app. Possible values are:</br>`submitted` — The specific version of the Teams app has been submitted and is under review. </br>`published`  — The request to publish the specific version of the Teams app has been approved by the admin and the app is published. </br> `rejected` — The request to publish the specific version of the Teams app was rejected by the admin. |
| displayName         | string   | The name of the app provided by the app developer. |
| version             | string   | The version number of the application. |
| shortDescription    | string   | Short description of the application. |
| description         | string   | Verbose description of the application. |

## Relationships

| Relationship | Type	| Description |
|:---------------|:--------|:----------|
|bot|[teamworkBot](teamworkbot.md) | The details of the bot specified in the Teams app manifest. |

## JSON representation

<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.teamsAppDefinition",
  "baseType": "microsoft.graph.entity"
}-->

```json
{
  "id": "string",
  "teamsAppId": "string",
  "displayName": "string",
  "version": "string"
}
```

## See also

- [teamsApp](teamsapp.md)
- [teamsAppInstallation](teamsappinstallation.md)
- [teamsTab](../resources/teamstab.md)

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "teamsApp resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

