---
title: "Remove attribute (from user flow)"
description: "Remove an attribute from an externalUsersSelfServiceSignupEventsFlow."
author: "nanguil"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: apiPageType
---

# Remove attribute (from user flow)
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Remove an attribute from an external identities self-service sign up user flow that's represented by an [externalUsersSelfServiceSignupEventsFlow](../resources/externalusersselfservicesignupeventsflow.md) object. You can add both custom and built-in attributes to a user flow.

After this step, [PATCH the user flow](../api/authenticationeventsflow-update.md) to remove the attribute from the attribute collection step.

## Permissions
Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "onattributecollectionexternalusersselfservicesignup_delete_attributes" } -->
[!INCLUDE [permissions-table](../includes/permissions/onattributecollectionexternalusersselfservicesignup-delete-attributes-permissions.md)]

[!INCLUDE [rbac-user-flows-convergence-apis-write](../includes/rbac-for-apis/rbac-user-flows-convergence-apis-write.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
DELETE /identity/authenticationEventsFlows/{authenticationEventsFlow-id}/microsoft.graph.externalUsersSelfServiceSignUpEventsFlow/onAttributeCollection/microsoft.graph.onAttributeCollectionExternalUsersSelfServiceSignUp/attributes/$ref
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
Don't supply a request body for this method.

## Response

If successful, this method returns a `204 No Content` response code.  If unsuccessful, a `4xx` error is returned with specific details.

## Examples

#### Request
Here's an example of a request that removes city as an attribute from the attribute collection step of an external identities self-service sign-up user flow. After executing this step, [update the attributes collected in the userflow](../api/authenticationeventsflow-update.md).
# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "delete_onAttributeCollectionExternalUsersSelfServiceSignUp"
}
-->
``` http
DELETE https://graph.microsoft.com/beta/identity/authenticationEventsFlows/0313cc37-d421-421d-857b-87804d61e33e/microsoft.graph.externalUsersSelfServiceSignUpEventsFlow/onAttributeCollection/microsoft.graph.onAttributeCollectionExternalUsersSelfServiceSignUp/attributes/$ref

{
    "@odata.id":"https://graph.microsoft.com/beta/identity/userFlowAttributes/city"
} 
```

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/delete-onattributecollectionexternalusersselfservicesignup-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/delete-onattributecollectionexternalusersselfservicesignup-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response
Here's an example of the response
<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 204 No Content
```
