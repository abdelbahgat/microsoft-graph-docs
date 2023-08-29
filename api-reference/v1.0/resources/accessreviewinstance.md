---
title: "accessReviewInstance resource type"
description: "Represents a recurrence of an accessReviewScheduleDefinition object."
author: "zhusijia26"
ms.localizationpriority: medium
ms.prod: "governance"
doc_type: resourcePageType
---

# accessReviewInstance resource type

Namespace: microsoft.graph

Represents an Azure AD [access review](accessreviewsv2-overview.md) recurrence. System-generated based off of the parent [accessReviewScheduleDefinition](accessreviewscheduledefinition.md) object. All properties are read-only.

If the instance is a part of a recurring access review, instances represent each recurrence. A review that does not recur will have exactly one instance. Instances also represent each unique resource being reviewed in the schedule definition. If a schedule definition reviews multiple resources, each resource will have a unique instance for each recurrence.

Every **accessReviewInstance** contains a list of [decisions](accessreviewinstancedecisionitem.md) that reviewers can take action on. There is one decision per identity being reviewed.

Inherits from [entity](../resources/entity.md).

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[List accessReviewInstances](../api/accessreviewscheduledefinition-list-instances.md)|[accessReviewInstance](../resources/accessreviewinstance.md) collection|Get a list of the [accessReviewInstance](../resources/accessreviewinstance.md) objects and their properties.|
|[Get accessReviewInstance](../api/accessreviewinstance-get.md)|[accessReviewInstance](../resources/accessreviewinstance.md)|Read the properties and relationships of an [accessReviewInstance](../resources/accessreviewinstance.md) object.|
|[Update accessReviewInstance](../api/accessreviewinstance-update.md)|[accessReviewInstance](../resources/accessreviewinstance.md)|Update the reviewers of an [accessReviewInstance](../resources/accessreviewinstance.md) object.|
|[filterByCurrentUser](../api/accessreviewinstance-filterbycurrentuser.md)|[accessReviewInstance](../resources/accessreviewinstance.md) collection|Returns all instance objects on a definition for which the calling user is the reviewer.|
|[List contacted reviewers](../api/accessreviewinstance-list-contactedreviewers.md)|[accessReviewReviewer](../resources/accessreviewreviewer.md) collection|Get the reviewers who received notifications for an access review instance.|
|[sendReminder](../api/accessreviewinstance-sendreminder.md)|None|Send a reminder to the reviewers of an accessReviewInstance.|
|[stop](../api/accessreviewinstance-stop.md)|None|Manually stop an accessReviewInstance.|
|[acceptRecommendations](../api/accessreviewinstance-acceptrecommendations.md)|None| Allows the calling user to accept the decision recommendation for each NotReviewed accessReviewInstanceDecisionItem that they are the reviewer on for a specific accessReviewInstance.|
|[applyDecisions](../api/accessreviewinstance-applydecisions.md)|None|Manually apply decision on an accessReviewInstance.|
|[batchRecordDecisions](../api/accessreviewinstance-batchrecorddecisions.md)|None|Review batches of principals or resources in one call.|
|[resetDecisions](../api/accessreviewinstance-resetdecisions.md)|None|Resets all decision items on an instance to `notReviewed`|
|[List decisions](../api/accessreviewinstance-list-decisions.md)|[accessReviewInstanceDecisionItem](../resources/accessreviewinstancedecisionitem.md) collection|Get the accessReviewInstanceDecisionItem resources from the decisions navigation property.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
| endDateTime | DateTimeOffset | DateTime when review instance is scheduled to end.The DatetimeOffset type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`. Supports `$select`. Read-only.|
| fallbackReviewers   |[accessReviewReviewerScope](../resources/accessreviewreviewerscope.md) collection| This collection of reviewer scopes is used to define the list of fallback reviewers. These fallback reviewers will be notified to take action if no users are found from the list of reviewers specified. This could occur when either the group owner is specified as the reviewer but the group owner does not exist, or manager is specified as reviewer but a user's manager does not exist. Supports `$select`.|
| id | String | Unique identifier of the instance. Inherited from [entity](../resources/entity.md). Supports `$select`. Read-only.|
| scope | [accessReviewScope](accessreviewscope.md) | Created based on **scope** and **instanceEnumerationScope** at the accessReviewScheduleDefinition level. Defines the scope of users reviewed in a group. Supports `$select` and `$filter` (`contains` only). Read-only. |
| startDateTime | DateTimeOffset | DateTime when review instance is scheduled to start. May be in the future. The DateTimeOffset type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`. Supports `$select`. Read-only. |
| status | String | Specifies the status of an accessReview. Possible values: `Initializing`, `NotStarted`, `Starting`, `InProgress`, `Completing`, `Completed`, `AutoReviewing`, and `AutoReviewed`. Supports `$select`, `$orderby`, and `$filter` (`eq` only). Read-only.|
| reviewers   |[accessReviewReviewerScope](../resources/accessreviewreviewerscope.md) collection| This collection of access review scopes is used to define who the reviewers are. Supports `$select`. For examples of options for assigning reviewers, see [Assign reviewers to your access review definition using the Microsoft Graph API](/graph/accessreviews-scope-concept).|


## Relationships
|Relationship|Type|Description|
|:---|:---|:---|
|decisions|[accessReviewInstanceDecisionItem](../resources/accessreviewinstancedecisionitem.md) collection|Each principal reviewed in an **accessReviewInstance** has a decision item representing if they were approved, denied, or not yet reviewed.|
| contactedReviewers   |[accessReviewReviewer](../resources/accessreviewreviewer.md) collection| Returns the collection of reviewers who were contacted to complete this review. While the **reviewers** and **fallbackReviewers** properties of the **accessReviewScheduleDefinition** might specify group owners or managers as **reviewers**, **contactedReviewers** returns their individual identities. Supports `$select`. Read-only. |

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.accessReviewInstance",
  "baseType": "microsoft.graph.entity",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.accessReviewInstance",
  "id": "String (identifier)",
  "startDateTime": "String (timestamp)",
  "endDateTime": "String (timestamp)",
  "status": "String",
  "scope": {
    "@odata.type": "microsoft.graph.accessReviewScope"
  },
  "reviewers": [
    {
      "@odata.type": "microsoft.graph.accessReviewReviewerScope"
    }
  ],
  "fallbackReviewers": [
    {
      "@odata.type": "microsoft.graph.accessReviewReviewerScope"
    }
  ]
}
```
