---
title: "accessPackageAssignmentRequestRequirements resource type"
description: "Identifies the requirements necessary to request the specified access package."
author: "markwahl-msft"
ms.localizationpriority: medium
ms.prod: "governance"
doc_type: resourcePageType
---
# accessPackageAssignmentRequestRequirements resource type

Namespace: microsoft.graph

Represents requirements that a caller must fulfill in order to successfully create an **accessPackageAssignmentRequest** for the **accessPackage** specified as part of the URL. Requirements are determined by evaluating policies associated with the **accessPackage**. 

## Properties
|Property|Type|Description|
|:---|:---|:---|
|allowCustomAssignmentSchedule|Boolean|Indicates whether the requestor is allowed to set a custom schedule.|
|isApprovalRequiredForAdd|Boolean|Indicates whether a request to add must be approved by an approver.|
|isApprovalRequiredForUpdate|Boolean|Indicates whether a request to update must be approved by an approver.|
|policyDescription|String|The description of the policy that the user is trying to request access using.|
|policyDisplayName|String|The display name of the policy that the user is trying to request access using.|
|policyId|String|The identifier of the policy that these requirements are associated with. This identifier can be used when creating a new assignment request.|
|schedule|[entitlementManagementSchedule](../resources/entitlementmanagementschedule.md)|Schedule restrictions enforced, if any.|

## Relationships
None.
## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.accessPackageAssignmentRequestRequirements"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.accessPackageAssignmentRequestRequirements",
  "policyId": "String",
  "policyDisplayName": "String",
  "policyDescription": "String",
  "isApprovalRequiredForAdd": "Boolean",
  "isApprovalRequiredForUpdate": "Boolean",
  "allowCustomAssignmentSchedule": "Boolean",
  "schedule": {
    "@odata.type": "microsoft.graph.entitlementManagementSchedule"
  }
}
```


