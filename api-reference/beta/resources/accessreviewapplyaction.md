---
title: "accessReviewApplyAction resource type"
description: "Represents the action to take on reviewed users after an access review instance is completed."
author: "jyothig123"
ms.localizationpriority: medium
ms.prod: "governance"
doc_type: resourcePageType
---

# accessReviewApplyAction resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

[!INCLUDE [accessreviews-disclaimer-v2](../../includes/accessreviews-disclaimer-v2.md)]

Represents a base class for apply actions in the [accessReviewScheduleSettings](accessreviewschedulesettings.md) of an [accessReviewScheduleDefinition](accessreviewscheduledefinition.md) object. The following derived types are supported:

- [removeAccessApplyAction](removeaccessapplyaction.md) indicates removing access of an entity being reviewed upon completion of the review. This is the default type for the applyActions property in accessReviewScheduleSettings and doesn't need to be specified.

- [disableAndDeleteUserApplyAction](disableanddeleteuserapplyaction.md) indicates disabling and deleting the user being reviewed upon completion of the review. This is the non-default type and must be explicitly specified in accessReviewScheduleSettings.

## Properties
None.

## Relationships
None.


## JSON representation
Here's a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.accessReviewApplyAction"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.accessReviewApplyAction"
}
```

<!--
{
  "type": "#page.annotation",
  "description": "accessReviewApplyAction resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->
