---
title: "plannerTeamsPublicationInfo resource type"
description: "Contains detailed information about the publication process that created a plannerTask."
author: "TarkanSevilmis"
ms.localizationpriority: medium
ms.prod: "planner"
doc_type: resourcePageType
---

# plannerTeamsPublicationInfo resource type

Namespace: microsoft.graph

Contains detailed information about the publication process that created a [plannerTask](plannertask.md). A publication process creates copies of tasks based on a template. These tasks are created in multiple plans, and have restricted permissions for the users; for example, they cannot be deleted and users might be blocked from editing certain fields. Publication is used to distribute tasks across an organization and track their progress centrally. This type derives from [plannerTaskCreation](plannerTaskCreation.md).

## Properties
|Property|Type|Description|
|:---|:---|:---|
|teamsPublicationInfo|[plannerTeamsPublicationInfo](../resources/plannerteamspublicationinfo.md)|Information about the publication process that created this task. This field is deprecated and should not be used in this resource type. Inherited from [plannerTaskCreation](plannerTaskCreation.md).|
|creationSourceKind|plannerCreationSourceKind|Specifies what kind of creation source the task is created with. The possible values are: `external`, `publication` and `unknownFutureValue`. The value of this property will be `publication`. Inherited from [plannerTaskCreation](plannerTaskCreation.md).|
|lastModifiedDateTime|DateTimeOffset|The date and time when this task was last modified by the publication process. Read-only. |
|publicationId|String| The identifier of the publication. Read-only.|
|publishedToPlanId|String|The identifier of the **plannerPlan** this task was originally placed in. Read-only. |
|publishingTeamId|String| The identifier of the [team](team.md) that initiated the publication process. Read-only.|
|publishingTeamName|String|The display name of the team that initiated the publication process. This display name is for reference only, and might not represent the most up-to-date name of the team. Read-only. |

## Relationships
None.

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.plannerTeamsPublicationInfo"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.plannerTeamsPublicationInfo",
  "creationSourceKind": "String-value",
  "publicationId": "String",
  "publishingTeamId": "String",
  "publishingTeamName": "String",
  "lastModifiedDateTime": "String (timestamp)",
  "publishedToPlanId": "String"
}
```

