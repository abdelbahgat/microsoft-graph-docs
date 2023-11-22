---
title: "List all (AWS identities)"
description: "Get a list of the awsIdentity objects and their properties."
author: "mrudulahg01"
ms.reviewer: ciem_pm
ms.localizationpriority: medium
ms.prod: "multicloud-permissions-management"
doc_type: apiPageType
---

# List all (AWS identities)
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a list of the [awsIdentity](../resources/awsidentity.md) objects and their properties.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|Not supported.|
|Delegated (personal Microsoft account)|Not supported.|
|Application|Not supported.|

<!--
[!INCLUDE [epm-rbac-servicenow-apis-read](../includes/rbac-for-apis/epm-rbac-servicenow-apis-read.md)]
-->

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /external/authorizationSystems/{id}/microsoft.graph.awsAuthorizationSystem/associatedIdentities/all
```

## Optional query parameters
This method supports the `$select`, `$filter`, `$count`, `$top`, and `$skipToken` OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [awsIdentity](../resources/awsidentity.md) objects in the response body.

## Examples

### Request
The following is an example of a request.
# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "list_awsidentity"
}
-->
``` http
GET https://graph.microsoft.com/beta/external/authorizationSystems/{id}/microsoft.graph.awsAuthorizationSystem/associatedIdentities/all
```

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/list-awsidentity-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/list-awsidentity-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---


### Response
The following is an example of the response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.awsIdentity)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#microsoft.graph.awsRole",
      "id": "YXJuOmF3czppYW06OjEyMzQ1Njc4OTAxMjpyb2xlL3NlcnZpY2Vyb2xlMQ",
      "externalId": "arn:aws:iam::123456789012:role/servicerole1",
      "displayName": "servicerole1",
      "roleType": "system",
      "trustEntityType": "service",
      "source": {
        "@odata.type": "#microsoft.graph.awsSource",
        "accountId": "123456789012",
        "identityProviderType": "aws"
      }
    },
    {
      "@odata.type": "#microsoft.graph.awsUser",
      "id": "YXJuOmF3czppYW06OjEyMzQ1Njc4OTAxMjp1c2VyL2JvYg",
      "externalId": "arn:aws:iam::123456789012:user/bob",
      "displayName": "bob smith",
      "source": {
        "@odata.type": "#microsoft.graph.awsSource",
        "accountId": "123456789012",
        "identityProviderType": "aws"
      }
    }
  ]
}
```

