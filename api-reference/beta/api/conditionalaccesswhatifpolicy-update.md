---
title: "Update conditionalAccessWhatIfPolicy"
description: "Update the properties of a conditionalAccessWhatIfPolicy object."
author: "**TODO: Provide GitHub Name. See [topic-level metadata reference](https://aka.ms/msgo?pagePath=Document-APIs/Guidelines/Metadata)**"
ms.localizationpriority: medium
ms.subservice: "**TODO: Add MS prod. See [topic-level metadata reference](https://aka.ms/msgo?pagePath=Document-APIs/Guidelines/Metadata)**"
doc_type: apiPageType
---

# Update conditionalAccessWhatIfPolicy

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of a [conditionalAccessWhatIfPolicy](../resources/conditionalaccesswhatifpolicy.md) object.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "conditionalaccesswhatifpolicy-update-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/conditionalaccesswhatifpolicy-update-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /conditionalAccessWhatIfPolicy
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|
|Content-Type|application/json. Required.|

## Request body

[!INCLUDE [table-intro](../../includes/update-property-table-intro.md)]


**TODO: Remove properties that don't apply**
|Property|Type|Description|
|:---|:---|:---|
|createdDateTime|DateTimeOffset|**TODO: Add Description** Inherited from [conditionalAccessPolicy](../resources/conditionalaccesspolicy.md). Optional.|
|modifiedDateTime|DateTimeOffset|**TODO: Add Description** Inherited from [conditionalAccessPolicy](../resources/conditionalaccesspolicy.md). Optional.|
|displayName|String|**TODO: Add Description** Inherited from [conditionalAccessPolicy](../resources/conditionalaccesspolicy.md). Required.|
|description|String|**TODO: Add Description** Inherited from [conditionalAccessPolicy](../resources/conditionalaccesspolicy.md). Optional.|
|state|conditionalAccessPolicyState|**TODO: Add Description** Inherited from [conditionalAccessPolicy](../resources/conditionalaccesspolicy.md). The possible values are: `enabled`, `disabled`, `enabledForReportingButNotEnforced`. Required.|
|conditions|[conditionalAccessConditionSet](../resources/conditionalaccessconditionset.md)|**TODO: Add Description** Inherited from [conditionalAccessPolicy](../resources/conditionalaccesspolicy.md). Required.|
|grantControls|[conditionalAccessGrantControls](../resources/conditionalaccessgrantcontrols.md)|**TODO: Add Description** Inherited from [conditionalAccessPolicy](../resources/conditionalaccesspolicy.md). Optional.|
|sessionControls|[conditionalAccessSessionControls](../resources/conditionalaccesssessioncontrols.md)|**TODO: Add Description** Inherited from [conditionalAccessPolicy](../resources/conditionalaccesspolicy.md). Optional.|
|policyApplies|Boolean|**TODO: Add Description** Required.|
|reasons|conditionalAccessWhatIfReasons collection|**TODO: Add Description**. The possible values are: `notSet`, `notEnoughInformation`, `invalidCondition`, `users`, `workloadIdentities`, `application`, `userActions`, `authenticationContext`, `devicePlatform`, `devices`, `clientApps`, `location`, `signInRisk`, `emptyPolicy`, `invalidPolicy`, `policyNotEnabled`, `userRisk`, `time`, `insiderRisk`, `authenticationFlow`, `unknownFutureValue`. Required.|



## Response

If successful, this method returns a `200 OK` response code and an updated [conditionalAccessWhatIfPolicy](../resources/conditionalaccesswhatifpolicy.md) object in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "update_conditionalaccesswhatifpolicy"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/conditionalAccessWhatIfPolicy
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.conditionalAccessWhatIfPolicy",
  "displayName": "String",
  "description": "String",
  "state": "String",
  "conditions": {
    "@odata.type": "microsoft.graph.conditionalAccessConditionSet"
  },
  "grantControls": {
    "@odata.type": "microsoft.graph.conditionalAccessGrantControls"
  },
  "sessionControls": {
    "@odata.type": "microsoft.graph.conditionalAccessSessionControls"
  },
  "policyApplies": "Boolean",
  "reasons": [
    "String"
  ]
}
```


### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.conditionalAccessWhatIfPolicy",
  "id": "a9c89169-2a7c-94ba-be1b-c02a83b6f273",
  "createdDateTime": "String (timestamp)",
  "modifiedDateTime": "String (timestamp)",
  "displayName": "String",
  "description": "String",
  "state": "String",
  "conditions": {
    "@odata.type": "microsoft.graph.conditionalAccessConditionSet"
  },
  "grantControls": {
    "@odata.type": "microsoft.graph.conditionalAccessGrantControls"
  },
  "sessionControls": {
    "@odata.type": "microsoft.graph.conditionalAccessSessionControls"
  },
  "policyApplies": "Boolean",
  "reasons": [
    "String"
  ]
}
```

