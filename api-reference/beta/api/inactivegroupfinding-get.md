---
title: "Get inactiveGroupFinding"
description: "Get details about an inactive group in AWS, Azure, or GCP environments."
author: "ashyasingh"
ms.reviewer: ciem_pm
ms.localizationpriority: medium
ms.prod: "multicloud-permissions-management"
doc_type: apiPageType
---

# Get inactiveGroupFinding

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get details about an [inactiveGroupFinding](../resources/inactivegroupfinding.md) object in AWS, Azure, or GCP environments.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|Not supported.|
|Delegated (personal Microsoft account)|Not supported.|
|Application|Not supported.|

## HTTP request

Get AWS inactive groups:
<!-- {
  "blockType": "ignored"
}
-->
```http
GET /identityGovernance/permissionsAnalytics/aws/findings/{id}/microsoft.graph.inactiveGroupFinding
```

Get Azure inactive groups:
<!-- {
  "blockType": "ignored"
}
-->
```http
GET /identityGovernance/permissionsAnalytics/azure/findings/{id}/microsoft.graph.inactiveGroupFinding
```

Get GCP inactive groups:
<!-- {
  "blockType": "ignored"
}
-->
```http
GET /identityGovernance/permissionsAnalytics/gcp/findings/{id}/microsoft.graph.inactiveGroupFinding
```

## Optional query parameters
This method does not support any OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [inactiveGroupFinding](../resources/inactivegroupfinding.md) objects in the response body.

## Examples

### Request

The following example shows a request for an inactive group in a GCP project.
# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "get_inactivegroupfinding"
}
-->
``` http
GET https://graph.microsoft.com/beta/identityGovernance/permissionsAnalytics/gcp/findings/MSxJbmFjdGl2ZUdyb3VwRmluZGluZyw2MDI0NA/microsoft.graph.inactiveGroupFinding
```

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-inactivegroupfinding-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-inactivegroupfinding-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.inactiveGroupFinding"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#identityGovernance/permissionsAnalytics/gcp/findings/microsoft.graph.inactiveGroupFinding/$entity",
    "id": "MSxJbmFjdGl2ZUdyb3VwRmluZGluZyw2MDI0NA",
    "createdDateTime": "2023-10-17T15:46:31.448597Z",
    "permissionsCreepIndex": {
        "score": 1
    },
    "actionSummary": {
        "assigned": 3011,
        "exercised": 0,
        "available": 7075
    },
    "group": {
        "@odata.type": "#microsoft.graph.gcpGroup",
        "id": "dGVzdGdyb3VwQGNsb3Vka25veC5pbw",
        "externalId": "testgroup@cloudknox.io",
        "displayName": "testgroup",
        "source": {
            "@odata.type": "#microsoft.graph.gsuiteSource",
            "identityProviderType": "gsuite",
            "domain": "carbide-bonsai-205017"
        },
        "authorizationSystem": {
            "@odata.type": "#microsoft.graph.gcpAuthorizationSystem",
            "authorizationSystemId": "carbide-bonsai-205017",
            "authorizationSystemName": "ck-staging",
            "authorizationSystemType": "gcp",
            "id": "MSxnY3AsY2FyYmlkZS1ib25zYWktMjA1MDE3"
        }
    }
}
```
