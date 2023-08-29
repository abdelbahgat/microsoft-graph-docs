---
title: "educationSubmission resource type"
description: "Represents the resources that an individual (or group) submit for an assignment and the outcomes (such as grades or feedback) associated with the submission."
author: "cristobal-buenrostro"
ms.localizationpriority: medium
ms.prod: "education"
doc_type: resourcePageType
---

# educationSubmission resource type

Namespace: microsoft.graph

Represents the resources that an individual (or group) turn in for an [assignment](educationassignment.md) and the outcomes (such as grades or feedback) that are associated with the **submission**.

Submissions are owned by an **assignment**. Submissions are automatically created when an **assignment** is published. The **submission** owns two lists of resources. Resources represent the user/groups working area while the submitted resources represent the resources that have actively been turned in by students.  

The **status** property is read-only and the object is moved through the workflow via actions. 

If [setUpResourcesFolder](../api/educationsubmission-setupResourcesFolder.md) has not been called on an **educationSubmission** resource, the **resourcesFolderUrl** property is `null`.

## Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[Get educationSubmission](../api/educationsubmission-get.md) | [educationSubmission](educationsubmission.md) |Read properties and relationships of an **educationSubmission** object.|
|[List resources](../api/educationsubmission-list-resources.md) |[educationSubmissionResource](educationsubmissionresource.md) collection| Get an **educationSubmissionResource** object collection.|
|[List submittedResources](../api/educationsubmission-list-submittedresources.md) |[educationSubmissionResource](educationsubmissionresource.md) collection| Get an **educationSubmissionResource** object collection.|
|[List outcomes](../api/educationsubmission-list-outcomes.md) |[educationOutcome](educationoutcome.md) collection| Get an **educationOutcome** object collection.|
|[return](../api/educationsubmission-return.md)|[educationSubmission](educationsubmission.md)|A teacher uses return to indicate that the grades/feedback can be shown to the student.|
|[reassign](../api/educationsubmission-reassign.md)|[educationSubmission](educationsubmission.md)|Reassign the submission to the student with feedback for review.|
|[Set up submission specific resources folder](../api/educationsubmission-setupResourcesFolder.md) |[educationSubmission](educationsubmission.md) | Create a SharePoint folder (under pre-defined location) to upload files as submission resources. |
|[submit](../api/educationsubmission-submit.md)|[educationSubmission](educationsubmission.md)|A student uses submit to turn in the **assignment**. This will copy the resources into the **submittedResources** folder for grading and updates the status.|
|[unsubmit](../api/educationsubmission-unsubmit.md)|[educationSubmission](educationsubmission.md)|A student uses the unsubmit to move the state of the submission from submitted back to working. This will copy the resources into the **workingResources** folder for grading and updates the status.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|String|Unique identifier for the submission.|
|recipient|[educationSubmissionRecipient](educationsubmissionrecipient.md)|Who this submission is assigned to.|
|returnedBy|[identitySet](identityset.md)|User who moved the status of this submission to returned.|
|returnedDateTime|DateTimeOffset|Moment in time when the submission was returned. The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`|
|resourcesFolderUrl|String|Folder where all file resources for this submission need to be stored.|
|status|string| Read-only. Possible values are: `working`, `submitted`, `released`, `returned`, and `reassigned`. Note that you must use the `Prefer: include-unknown-enum-members` request header to get the following value(s) in this [evolvable enum](/graph/best-practices-concept#handling-future-members-in-evolvable-enumerations): `reassigned`.|
|submittedBy|[identitySet](identityset.md)|User who moved the resource into the submitted state.|
|submittedDateTime|DateTimeOffset|Moment in time when the submission was moved into the submitted state. The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`|
|unsubmittedBy|[identitySet](identityset.md)|User who moved the resource from submitted into the working state.|
|unsubmittedDateTime|DateTimeOffset|Moment in time when the submission was moved from submitted into the working state. The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`|
|reassignedBy|[identitySet](identityset.md)|User who moved the status of this submission to reassigned.|
|reassignedDateTime|DateTimeOffset|Moment in time when the submission was reassigned. The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`|

## Relationships
| Relationship | Type	|Description|
|:---------------|:--------|:----------|
|resources|[educationSubmissionResource](educationsubmissionresource.md) collection| Nullable.|
|submittedResources|[educationSubmissionResource](educationsubmissionresource.md) collection| Read-only. Nullable.|
|outcomes|[educationOutcome](educationOutcome.md) collection. Holds grades, feedback and/or rubrics information the teacher assigns to this submission|Read-Write. Nullable.|

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.educationSubmission"
}-->

```json
{
    "id":"String (identifier)",
    "recipient":{"@odata.type":"microsoft.graph.educationSubmissionRecipient"},
    "returnedBy":{"@odata.type":"microsoft.graph.identitySet"},
    "returnedDateTime":"String (timestamp)",
    "resourcesFolderUrl":"String",
    "status":"string",
    "submittedBy":{"@odata.type":"microsoft.graph.identitySet"},
    "submittedDateTime":"String (timestamp)",
    "unsubmittedBy":{"@odata.type":"microsoft.graph.identitySet"},
    "unsubmittedDateTime":"String (timestamp)",
    "reassignedBy":{"@odata.type":"microsoft.graph.identitySet"},
    "reassignedDateTime":"String (timestamp)"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "educationSubmission resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


