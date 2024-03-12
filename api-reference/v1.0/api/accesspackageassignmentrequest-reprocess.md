---
title: "accessPackageAssignmentRequest: reprocess"
description: "Reprocess accessPackageAssignmentRequest objects."
ms.localizationpriority: medium
author: "markwahl-msft"
ms.prod: "governance"
doc_type: "apiPageType"
---

# accessPackageAssignmentRequest: reprocess

Namespace: microsoft.graph

In [Azure AD entitlement management](../resources/entitlementmanagement-overview.md), callers can automatically retry a user's request for access to an access package. It is performed on an [accessPackageAssignmentRequest](../resources/accesspackageassignmentrequest.md) object whose **requestState** is in a `DeliveryFailed` or `PartiallyDelivered` state. 

You can only reprocess a request within 14 days from the time the original request was completed. For requests completed more than 14 days, you will need to ask the users to cancel the request(s) and make a new request in the [MyAccess](https://myaccess.microsoft.com/) portal.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
|:---------------------------------------|:--------------------------------------------|
| Delegated (work or school account) | EntitlementManagement.ReadWrite.All |
| Delegated (personal Microsoft account) | Not supported. |
| Application | EntitlementManagement.ReadWrite.All |
  
## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
```http
POST /identityGovernance/entitlementManagement/assignmentRequests/{id}/reprocess
```

## Request headers

| Name      |Description|
|:----------|:----------|
| Authorization | Bearer \{token\}. Required. |

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a  `202 Accepted` response code and retries the request. If the [accessPackageAssignmentRequest](../resources/accesspackageassignmentrequest.md) object doesn't exist, this method will return `404 Not Found` or if the **id** isn't valid, this method returns a `400 Bad Request` response code.

## Examples

### Request

The following is an example of the request.

<!-- {
  "blockType": "ignored",
  "name": "reprocess_accesspackageassignmentrequest"
}-->
```http
POST https://graph.microsoft.com/v1.0/identityGovernance/entitlementManagement/assignmentRequests/d82eb508-acc4-43cc-bcf1-7c1c4a2c073b/reprocess
```

### Response

The following is an example of the response.


<!-- {
  "blockType": "response",
  "truncated": true
} -->

```http
HTTP/1.1 202 Accepted  
```
