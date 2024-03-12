---
title: "accessReviewStageSettings resource type"
description: "Represents the settings of the stages that are associated with a multi-stage access review."
author: "isabelleatmsft"
ms.localizationpriority: medium
ms.prod: "governance"
doc_type: resourcePageType
---

# accessReviewStageSettings resource type

Namespace: microsoft.graph

Represents the settings of the stages that are associated with a [multi-stage access review](accessreviewscheduledefinition.md) object. 

## Properties
|Property|Type|Description|
|:---|:---|:---|
|decisionsThatWillMoveToNextStage|String collection|Indicate which decisions will go to the next stage. Can be a sub-set of `Approve`, `Deny`, `Recommendation`, or `NotReviewed`. If not provided, all decisions will go to the next stage. Optional. |
|dependsOn|String collection| Defines the sequential or parallel order of the stages and depends on the **stageId**. Only sequential stages are currently supported. For example, if **stageId** is `2`, then **dependsOn** must be `1`. If **stageId** is `1`, do not specify **dependsOn**. Required if **stageId** is not `1`. |
|durationInDays|Int32|The duration of the stage. Required.  <br/><br/>**NOTE:** The cumulative value of this property across all stages <br/> 1. Will override the [instanceDurationInDays setting](accessReviewScheduleSettings.md) on the [accessReviewScheduleDefinition](accessReviewScheduleDefinition.md) object. <br/>2. Cannot exceed the length of one recurrence. That is, if the review recurs weekly, the cumulative **durationInDays** cannot exceed 7. |
|fallbackReviewers|[accessReviewReviewerScope](../resources/accessreviewreviewerscope.md) collection|If provided, the fallback reviewers are asked to complete a review if the primary reviewers do not exist. For example, if managers are selected as **reviewers** and a principal under review does not have a manager in Azure AD, the fallback reviewers are asked to review that principal. <br/><br/>**NOTE:** The value of this property will override the corresponding setting on the [accessReviewScheduleDefinition](accessReviewScheduleDefinition.md) object.|
|recommendationsEnabled|Boolean|Indicates whether showing recommendations to reviewers is enabled. Required. <br/><br/>**NOTE:** The value of this property will override override the corresponding [setting](accessReviewScheduleSettings.md) on the [accessReviewScheduleDefinition](accessreviewscheduledefinition.md) object.|
|reviewers|[accessReviewReviewerScope](../resources/accessreviewreviewerscope.md) collection|Defines who the reviewers are. If none are specified, the review is a self-review (users review their own access).  For examples of options for assigning reviewers, see [Assign reviewers to your access review definition using the Microsoft Graph API](/graph/accessreviews-reviewers-concept). <br/><br/>**NOTE:** The value of this property will override the corresponding setting on the [accessReviewScheduleDefinition](accessReviewScheduleDefinition.md). |
|stageId|String|Unique identifier of the **accessReviewStageSettings** object. The **stageId** will be used by the **dependsOn** property to indicate the order of the stages. Required. |

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.accessReviewStageSettings"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.accessReviewStageSettings",
  "dependsOn": [
    "String"
  ],
  "durationInDays": "Integer",
  "decisionsThatWillMoveToNextStage": [
    "String"
  ],
  "fallbackReviewers": [
    {
      "@odata.type": "microsoft.graph.accessReviewReviewerScope"
    }
  ],
  "recommendationsEnabled": "Boolean",
  
  "reviewers": [
    {
      "@odata.type": "microsoft.graph.accessReviewReviewerScope"
    }
  ],
  "stageId": "String"
}
```

