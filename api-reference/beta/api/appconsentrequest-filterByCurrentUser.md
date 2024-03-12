---
title: "appConsentRequest: filterByCurrentUser"
description: "Retrieve appConsentRequest objects for which the current user is the reviewer."
author: "psignoret"
ms.localizationpriority: medium
ms.prod: "governance"
doc_type: apiPageType
---

# appConsentRequest: filterByCurrentUser
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Retrieve a collection of [appConsentRequest](../resources/appconsentrequest.md) objects for which the current user is the reviewer and the status of the userConsentRequest for accessing the specified app is `InProgress`.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|ConsentRequest.Read.All, ConsentRequest.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|ConsentRequest.Read.All, ConsentRequest.ReadWrite.All|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /identityGovernance/appConsent/appConsentRequests/filterByCurrentUser(on='parameterValue')
```

## Function parameters
In the request URL, provide the following query parameters with values.
The following table shows the parameters that can be used with this function.

|Property|Type|Description|
|:---|:---|:---|
|on|consentRequestFilterByCurrentUserOptions|Filter to query appConsentRequest objects for which the current user is a reviewer. Allowed value is `reviewer`. Required.|

## Query parameters
This function *requires* the `$filter` (`eq`) OData query parameter to return a collection of [userConsentRequest](../resources/userconsentrequest.md) objects for which the status is `InProgress`. The function also supports the `$select` query parameter. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [appConsentRequest](../resources/appconsentrequest.md) objects in the response body.

## Example 1: List all appConsentRequests

### Request

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "appconsentrequest_filterbycurrentuser"
}
-->
``` http
GET https://graph.microsoft.com/beta/identityGovernance/appConsent/appConsentRequests/filterByCurrentUser(on='reviewer')?$filter=userConsentRequests/any(u:u/status eq 'InProgress')
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/appconsentrequest-filterbycurrentuser-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/appconsentrequest-filterbycurrentuser-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/appconsentrequest-filterbycurrentuser-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/appconsentrequest-filterbycurrentuser-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/appconsentrequest-filterbycurrentuser-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/appconsentrequest-filterbycurrentuser-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.appConsentRequest)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#Collection(appConsentRequest)",
    "@odata.count": 1,
    "value": [
        {
            "@odata.type": "#microsoft.graph.appConsentRequest",
            "id": "7322e5f3-0f15-4eb8-9e82-2029e8622f5d",
            "appId": "de8bc8b5-d9f9-48b1-a8ad-b748da725064",
            "appDisplayName": "Graph Explorer",
            "consentType": "Dynamic",
            "pendingScopes": [
                {
                    "displayName": "AccessReview.Read.All"
                },
                {
                    "displayName": "openid"
                },
                {
                    "displayName": "profile"
                },
                {
                    "displayName": "offline_access"
                }
            ],
            "userConsentRequests": []
        }
    ]
}
```

