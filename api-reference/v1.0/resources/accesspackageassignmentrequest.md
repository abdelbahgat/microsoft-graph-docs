---
title: "accessPackageAssignmentRequest resource type"
description: "An access package assignment request is created by a user who wants to obtain an access package assignment."
author: "markwahl-msft"
ms.localizationpriority: medium
ms.prod: "governance"
doc_type: resourcePageType
---
# accessPackageAssignmentRequest resource type

Namespace: microsoft.graph


In [Azure AD Entitlement Management](entitlementmanagement-overview.md), an access package assignment request is created by or on behalf of a user who wants to obtain an access package assignment. If the request is successful, with any necessary approvals, the user receives an access package assignment, and is the subject of that resulting access package assignment.  Azure AD also creates access package assignment requests automatically for tracking access removal.

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[List accessPackageAssignmentRequests](../api/entitlementmanagement-list-assignmentrequests.md)|[accessPackageAssignmentRequest](accesspackageassignmentrequest.md) collection|Retrieve a list of **accesspackageassignmentrequest** objects. |
| [Create accessPackageAssignmentRequest](../api/entitlementmanagement-post-assignmentrequests.md) | [accessPackageAssignmentRequest](accesspackageassignmentrequest.md) | Creates a new **accessPackageAssignmentRequest** object. |
|[Get accessPackageAssignmentRequest](../api/accesspackageassignmentrequest-get.md)|[accessPackageAssignmentRequest](accesspackageassignmentrequest.md)|Read properties and relationships of an **accessPackageAssignmentRequest** object. |
|[Delete accessPackageAssignmentRequest](../api/accesspackageassignmentrequest-delete.md)|None|Delete an **accessPackageAssignmentRequest**. |
|[filterByCurrentUser](../api/accesspackageassignmentrequest-filterbycurrentuser.md)|[accessPackageAssignmentRequest](../resources/accesspackageassignmentrequest.md) collection|Retrieve the list of **accessPackageAssignmentRequest** objects filtered on the signed-in user.|
|[cancel](../api/accesspackageassignmentrequest-cancel.md)|[accessPackageAssignmentRequest](../resources/accesspackageassignmentrequest.md) collection|Cancel an **accessPackageAssignmentRequest** object that is in a cancellable state.|
|[reprocess](../api/accesspackageassignmentrequest-reprocess.md) | None | Automatically retry a user’s request for access to an access package.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
|completedDateTime|DateTimeOffset|The date of the end of processing, either successful or failure, of a request. The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`. Read-only.|
|createdDateTime|DateTimeOffset|The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`. Read-only.|
|id|String|Read-only.|
|requestType|accessPackageRequestType|The type of the request. The possible values are: `notSpecified`, `userAdd`, `userUpdate`, `userRemove`, `adminAdd`, `adminUpdate`, `adminRemove`, `systemAdd`, `systemUpdate`, `systemRemove`, `onBehalfAdd`, `unknownFutureValue`. A request from the user themselves would have requestType of `UserAdd` or `UserRemove`. This property cannot be changed once set.|
|schedule|[entitlementManagementSchedule](../resources/entitlementmanagementschedule.md)|The range of dates that access is to be assigned to the requestor. This property cannot be changed once set.|
|state|accessPackageRequestState|The state of the request. The possible values are: `submitted`, `pendingApproval`, `delivering`, `delivered`, `deliveryFailed`, `denied`, `scheduled`, `canceled`, `partiallyDelivered`, `unknownFutureValue`. Read-only.|
|status|String|More information on the request processing status. Read-only.|

## Relationships
|Relationship|Type|Description|
|:---|:---|:---|
|accessPackage|[accessPackage](../resources/accesspackage.md)|The access package associated with the accessPackageAssignmentRequest. An access package defines the collections of resource roles and the policies for how one or more users can get access to those resources. Read-only. Nullable. <br/><br/> Supports `$expand`.|
|assignment|[accessPackageAssignment](../resources/accesspackageassignment.md)|For a **requestType** of `UserAdd` or `AdminAdd`, this is an access package assignment requested to be created.  For a **requestType** of `UserRemove`, `AdminRemove` or `SystemRemove`, this has the `id` property of an existing assignment to be removed.  <br/><br/> Supports `$expand`.|
|requestor|[accessPackageSubject](../resources/accesspackagesubject.md)|The subject who requested or, if a direct assignment, was assigned. Read-only. Nullable. Supports `$expand`.|

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.accessPackageAssignmentRequest",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.accessPackageAssignmentRequest",
  "id": "String (identifier)",
  "requestType": "String",
  "state": "String",
  "status": "String",
  "createdDateTime": "String (timestamp)",
  "completedDateTime": "String (timestamp)",
  "schedule": {
    "@odata.type": "microsoft.graph.entitlementManagementSchedule"
  }
}
```


