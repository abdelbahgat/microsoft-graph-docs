---
title: "Create assignmentPolicies"
description: "Create a new accessPackageAssignmentPolicy object."
author: "markwahl-msft"
ms.localizationpriority: medium
ms.prod: "governance"
doc_type: apiPageType
---
# Create assignmentPolicies
Namespace: microsoft.graph

In [Azure AD entitlement management](../resources/entitlementmanagement-overview.md), create a new [accessPackageAssignmentPolicy](../resources/accesspackageassignmentpolicy.md) object.  The request will include a reference to the [accessPackage](../resources/accesspackage.md) that will contain this policy, which must already exist.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
|:---------------------------------------|:--------------------------------------------|
| Delegated (work or school account)     | EntitlementManagement.ReadWrite.All  |
| Delegated (personal Microsoft account) | Not supported. |
| Application                            | EntitlementManagement.ReadWrite.All |


## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /identityGovernance/entitlementManagement/assignmentPolicies
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply a JSON representation of the [accessPackageAssignmentPolicy](../resources/accesspackageassignmentpolicy.md) object.

You can specify the following properties when creating an **accessPackageAssignmentPolicy**.

|Property|Type|Description|
|:---|:---|:---|
|description|String|The description of the policy.|
|displayName|String|The display name of the policy.|
|allowedTargetScope|allowedTargetScope|Who is allowed to be assigned the access package through this policy. The possible values are: `notSpecified`, `specificDirectoryUsers`, `specificConnectedOrganizationUsers`, `specificDirectoryServicePrincipals`, `allMemberUsers`, `allDirectoryUsers`, `allDirectoryServicePrincipals`, `allConfiguredConnectedOrganizationUsers`, `allExternalUsers`, `unknownFutureValue`. Optional.|
|expiration|[expirationPattern](../resources/expirationpattern.md)|The expiration date for assignments created in this policy.|
|requestApprovalSettings|[accessPackageAssignmentApprovalSettings](../resources/accesspackageassignmentapprovalsettings.md)|Specifies the settings for approval of requests for an access package assignment through this policy. For example, if approval is required for new requests.|
|requestorSettings|[accessPackageAssignmentRequestorSettings](../resources/accesspackageassignmentrequestorsettings.md)|Provides additional settings to select who can create a request for an access package assignment through this policy, and what they can include in their request.|
|reviewSettings|[accessPackageAssignmentReviewSettings](../resources/accesspackageassignmentreviewsettings.md)|Settings for access reviews of assignments through this policy.|
|specificAllowedTargets|[subjectSet](../resources/subjectset.md) collection|The targets for being assigned access from an access package from this policy.|
|accessPackage|[accessPackage](../resources/accesspackage.md)| A reference to the access package that will contain the policy, which must already exist.|

## Response

If successful, this method returns a `201 Created` response code and an [accessPackageAssignmentPolicy](../resources/accesspackageassignmentpolicy.md) object in the response body.

## Examples

### Example 1: Create a direct assignment policy

A direct assignment policy is useful when access package assignment requests will only be created by an administrator, not by users themselves.

#### Request

The following example shows a request to create an access package assignment policy. In this policy, no users can request, no approval is required, and there are no access reviews.


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "create_accesspackageassignmentpolicy_from_"
}
-->
``` http
POST https://graph.microsoft.com/v1.0/identityGovernance/entitlementManagement/assignmentPolicies
Content-Type: application/json

{
  "displayName": "New Policy",
  "description": "policy for assignment",
  "allowedTargetScope": "notSpecified",
  "specificAllowedTargets": [],
  "expiration": {
      "endDateTime": null,
      "duration": null,
      "type": "noExpiration"
  },
  "requestorSettings": {
      "enableTargetsToSelfAddAccess": false,
      "enableTargetsToSelfUpdateAccess": false,
      "enableTargetsToSelfRemoveAccess": false,
      "allowCustomAssignmentSchedule": true,
      "enableOnBehalfRequestorsToAddAccess": false,
      "enableOnBehalfRequestorsToUpdateAccess": false,
      "enableOnBehalfRequestorsToRemoveAccess": false,
      "onBehalfRequestors": []
  },
  "requestApprovalSettings": {
      "isApprovalRequiredForAdd": false,
      "isApprovalRequiredForUpdate": false,
      "stages": []
  },
  "accessPackage": {
      "id": "a2e1ca1e-4e56-47d2-9daa-e2ba8d12a82b"
  }
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/create-accesspackageassignmentpolicy-from--csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/create-accesspackageassignmentpolicy-from--javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/create-accesspackageassignmentpolicy-from--java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/create-accesspackageassignmentpolicy-from--go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/create-accesspackageassignmentpolicy-from--powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/create-accesspackageassignmentpolicy-from--php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---


#### Response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.accessPackageAssignmentPolicy"
}
-->
``` http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "id": "87e1c7f7-c7f7-87e1-f7c7-e187f7c7e187",
  "displayName": "New policy",
  "description": "policy for assignment"
}
```

### Example 2: Create a policy for users from other organizations to request

The following example shows a more complex policy with two stages of approval and recurring access reviews.

#### Request


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "create_accesspackageassignmentpolicy_2"
}
-->
```http
POST https://graph.microsoft.com/v1.0/identityGovernance/entitlementManagement/assignmentPolicies
Content-Type: application/json

{
    "displayName": "policy for external access requests",
    "description": "policy for users from connected organizations to request access, with two stages of approval.",
    "allowedTargetScope": "allConfiguredConnectedOrganizationUsers",
    "specificAllowedTargets": [],
    "expiration": {
        "type": "noExpiration"
    },
    "requestorSettings": {
        "enableTargetsToSelfAddAccess": true,
        "enableTargetsToSelfUpdateAccess": true,
        "enableTargetsToSelfRemoveAccess": true,
        "allowCustomAssignmentSchedule": false,
        "enableOnBehalfRequestorsToAddAccess": false,
        "enableOnBehalfRequestorsToUpdateAccess": false,
        "enableOnBehalfRequestorsToRemoveAccess": false,
        "onBehalfRequestors": []
    },
    "requestApprovalSettings": {
        "isApprovalRequiredForAdd": true,
        "isApprovalRequiredForUpdate": false,
        "stages": [
            {
                "durationBeforeAutomaticDenial": "P14D",
                "isApproverJustificationRequired": false,
                "isEscalationEnabled": false,
                "durationBeforeEscalation": "PT0S",
                "primaryApprovers": [
                    {
                        "@odata.type": "#microsoft.graph.internalSponsors"
                    }
                ],
                "fallbackPrimaryApprovers": [
                    {
                        "@odata.type": "#microsoft.graph.singleUser",
                        "userId": "7deff43e-1f17-44ef-9e5f-d516b0ba11d4"
                    },
                    {
                        "@odata.type": "#microsoft.graph.groupMembers",
                        "groupId": "1623f912-5e86-41c2-af47-39dd67582b66"
                    }
                ],
                "escalationApprovers": [],
                "fallbackEscalationApprovers": []
            },
            {
                "durationBeforeAutomaticDenial": "P14D",
                "isApproverJustificationRequired": false,
                "isEscalationEnabled": false,
                "durationBeforeEscalation": "PT0S",
                "primaryApprovers": [],
                "fallbackPrimaryApprovers": [
                    {
                        "@odata.type": "#microsoft.graph.singleUser",
                        "userId": "46184453-e63b-4f20-86c2-c557ed5d5df9"
                    },
                    {
                        "@odata.type": "#microsoft.graph.groupMembers",
                        "groupId": "1623f912-5e86-41c2-af47-39dd67582b66"
                    }
                ],
                "escalationApprovers": [],
                "fallbackEscalationApprovers": []
            }
        ]
    },
    "reviewSettings": {
        "isEnabled": true,
        "expirationBehavior": "keepAccess",
        "isRecommendationEnabled": true,
        "isReviewerJustificationRequired": true,
        "isSelfReview": false,
        "schedule": {
            "startDateTime": "2022-07-02T06:59:59.998Z",
            "expiration": {
                "duration": "P14D",
                "type": "afterDuration"
            },
            "recurrence": {
                "pattern": {
                    "type": "absoluteMonthly",
                    "interval": 3,
                    "month": 0,
                    "dayOfMonth": 0,
                    "daysOfWeek": []
                },
                "range": {
                    "type": "noEnd",
                    "numberOfOccurrences": 0
                }
            }
        },
        "primaryReviewers": [
            {
                "@odata.type": "#microsoft.graph.groupMembers",
                "groupId": "1623f912-5e86-41c2-af47-39dd67582b66"
            }
        ],
        "fallbackReviewers": []
    },
    "accessPackage": {
        "id": "a2e1ca1e-4e56-47d2-9daa-e2ba8d12a82b"
    }
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/create-accesspackageassignmentpolicy-2-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/create-accesspackageassignmentpolicy-2-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/create-accesspackageassignmentpolicy-2-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/create-accesspackageassignmentpolicy-2-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/create-accesspackageassignmentpolicy-2-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/create-accesspackageassignmentpolicy-2-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---


#### Response

>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.accessPackageAssignmentPolicy"
}
-->
``` http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "id": "9d8f2361-39be-482e-b267-34ad6baef4d3",
    "displayName": "policy for external access requests",
    "description": "policy for users from connected organizations to request access, with two stages of approval."
}
```

