---
title: "Create accessPackageAssignmentRequest"
description: "Create a new accessPackageAssignmentRequest."
author: "markwahl-msft"
ms.localizationpriority: medium
ms.prod: "governance"
doc_type: apiPageType
---
# Create accessPackageAssignmentRequest

Namespace: microsoft.graph


In [Azure AD Entitlement Management](../resources/entitlementmanagement-overview.md), create a new [accessPackageAssignmentRequest](../resources/accesspackageassignmentrequest.md) object.  This operation is used to assign a user to an access package, or to remove an access package assignment.


## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
|:---------------------------------------|:--------------------------------------------|
| Delegated (work or school account)     | EntitlementManagement.ReadWrite.All |
| Delegated (personal Microsoft account) | Not supported. |
| Application                            | EntitlementManagement.ReadWrite.All |

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /identityGovernance/entitlementManagement/assignmentRequests
```

## Request headers

| Name          | Description   |
|:--------------|:--------------|
| Authorization | Bearer \{token\}. Required. |
| Content-Type  | application/json. Required. |

## Request body

In the request body, supply a JSON representation of [accessPackageAssignmentRequest](../resources/accesspackageassignmentrequest.md) object.

For an administrator to request to create an assignment for a user, the value of the **requestType** property is `AdminAdd`, and the **assignment** property contains the `targetId` of the user being assigned, the **assignmentPolicyId** property identifying the [accessPackageAssignmentPolicy](../resources/accesspackageassignmentpolicy.md), and the **accessPackageId** property identifying the [accessPackage](../resources/accesspackage.md).

For an administrator to request to remove an assignment, the value of the **requestType** property is `AdminRemove`, and the **assignment** property contains the **id** property identifying the [accessPackageAssignment](../resources/accesspackageassignment.md) being removed.

For a non-administrator user to request to create their own assignment for either a first assignment or renew assignment, the value of the **requestType** property is `UserAdd`. The **assignment** property contains an object with the `targetId` with the `id` of the user. The **assignmentPolicyId** property identifies the [accessPackageAssignmentPolicy](../resources/accesspackageassignmentpolicy.md). The **accessPackageId** property identifies the [accessPackage](../resources/accesspackage.md). The user making the request must already exist in the directory.

For a non-administrator user to request to extend their own assignments, the value of the **requestType** property is `UserExtend`. The **assignment** property contains the `targetId` with the `id` of the users. The **assignmentPolicyId** property identifies the [accessPackageAssignmentPolicy](../resources/accesspackageassignmentpolicy.md). The **accessPackageId** property identifies the [accessPackage](../resources/accesspackage.md). The user making the request must already exist in the directory.

## Response

If successful, this method returns a 200-series response code and a new [accessPackageAssignmentRequest](../resources/accesspackageassignmentrequest.md) object in the response body.

If this is an `AdminAdd` request, then subsequently an [accessPackageAssignment](../resources/accesspackageassignment.md) and, if needed, an [accessPackageSubject](../resources/accesspackagesubject.md) are also created. You can locate those using the query parameters when [listing accessPackageAssignments](entitlementmanagement-list-assignments.md).

## Examples

### Example 1: Admin requests a direct assignment for a user already in the directory
#### Request

The following is an example of the request for a direct assignment, in which the administrator is requesting the creation of an assignment for the user. Because the [accessPackageSubject](../resources/accesspackagesubject.md) might not yet exist, the value of the **targetID** is the object ID of the user being assigned, the value of the **accessPackageId** is the desired access package for that user, and the value of **assignmentPolicyId** is a direct assignment policy in that access package.



# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "create_accesspackageassignmentrequest_from_accesspackageassignmentrequests_1"
}-->

```http
POST https://graph.microsoft.com/v1.0/identityGovernance/entitlementManagement/assignmentRequests
Content-type: application/json

{
  "requestType": "AdminAdd",
  "assignment":{
     "targetId":"46184453-e63b-4f20-86c2-c557ed5d5df9",
     "assignmentPolicyId":"2264bf65-76ba-417b-a27d-54d291f0cbc8",
     "accessPackageId":"a914b616-e04e-476b-aa37-91038f0b165b"
  }
}
```

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/create-accesspackageassignmentrequest-from-accesspackageassignmentrequests-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/create-accesspackageassignmentrequest-from-accesspackageassignmentrequests-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/create-accesspackageassignmentrequest-from-accesspackageassignmentrequests-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/create-accesspackageassignmentrequest-from-accesspackageassignmentrequests-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---


#### Response

The following is an example of the response.

> **Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.accessPackageAssignmentRequest"
} -->

```http
HTTP/1.1 201 Created
Content-type: application/json

{

  "id": "7e382d02-4454-436b-b700-59c7dd77f466",
  "requestType": "AdminAdd",
  "requestState": "Submitted",
  "requestStatus": "Accepted"
}
```

### Example 2: Remove an assignment

To remove assignments, create a new accessPackageAssignmentRequest object with the following settings:

+ The value of the **requestType** property set to `AdminRemove`.
+ In the assignment property, include an object with the identifier of the accessPackageAssignment object to delete.

#### Request

The following example shows how to remove an assignment.


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "create_accesspackageassignmentrequest_from_accesspackageassignmentrequests"
}-->

```http
POST https://graph.microsoft.com/v1.0/identityGovernance/entitlementManagement/assignmentRequests
Content-type: application/json

{
    "requestType": "AdminRemove",
    "assignment":{
     "id": "a6bb6942-3ae1-4259-9908-0133aaee9377"
    }
}
```
# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/create-accesspackageassignmentrequest-from-accesspackageassignmentrequests-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/create-accesspackageassignmentrequest-from-accesspackageassignmentrequests-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Objective-C](#tab/objc)
[!INCLUDE [sample-code](../includes/snippets/objc/create-accesspackageassignmentrequest-from-accesspackageassignmentrequests-objc-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/create-accesspackageassignmentrequest-from-accesspackageassignmentrequests-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/create-accesspackageassignmentrequest-from-accesspackageassignmentrequests-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/create-accesspackageassignmentrequest-from-accesspackageassignmentrequests-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---


#### Response

The following is an example of the response.

> **Note:** The response object shown here might be shortened for readability. All the properties will be returned from an actual call.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.accessPackageAssignmentRequest"
} -->

```http
HTTP/1.1 201 Created
Content-type: application/json

{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#accessPackageAssignmentRequests/$entity",

    "id": "78eaee8c-e6cf-48c9-8f99-aae44c35e379",
    "requestType": "AdminRemove",
    "requestState": "Submitted",
    "requestStatus": "Accepted"
}
```

### Example 3: Request an assignment

The following example shows how a user can request an access package assignment for themselves.

#### Request

<!-- {
  "blockType": "request",
  "name": "create_accesspackageassignmentrequest_from_accesspackageassignmentrequests"
}-->
```http
POST https://graph.microsoft.com/v1.0/identityGovernance/entitlementManagement/assignmentRequests
Content-type: application/json

{
    "requestType": "userAdd",
    "assignment": {
        "accessPackageId": "d7be3253-b9c6-4fab-adef-30d30de8da2b"
    }
}
```

#### Response

The following is an example of the response.

> **Note:** The response object shown here might be shortened for readability. All the properties will be returned from an actual call.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.accessPackageAssignmentRequest"
} -->

```http
HTTP/1.1 201 Created
Content-type: application/json

{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#identityGovernance/entitlementManagement/assignmentRequests/$entity",
    "id": "724bc62d-90ff-48f3-903f-b59ec8453343",
    "requestType": "userAdd",
    "state": "submitted"
}
```

