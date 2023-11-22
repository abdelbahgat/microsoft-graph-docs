---
title: "Get payload"
description: "Get an attack simulation campaign payload for a tenant."
author: "stuartcl"
ms.localizationpriority: medium
ms.prod: "security"
doc_type: apiPageType
---

# Get payload

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get an attack simulation campaign payload for a tenant.

[!INCLUDE [national-cloud-support](../../includes/global-only.md)]

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "payload_get" } -->
[!INCLUDE [permissions-table](../includes/permissions/payload-get-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /security/attackSimulation/payloads/{payloadId}
```

## Optional query parameters

This method does not currently support the [OData query parameters](/graph/query-parameters) to customize the response.

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a [payload](../resources/payload.md) object in the response body.

## Examples

### Request

The following is an example of a request.

<!-- {
  "blockType": "request",
  "name": "get_payload",
  "sampleKeys": ["f1b13829-3829-f1b1-2938-b1f12938b1a"]
}
-->
``` http
GET https://graph.microsoft.com/beta/security/attackSimulation/payload/f1b13829-3829-f1b1-2938-b1f12938b1a
```

### Response

The following example shows the response.

>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.payload"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.context": "https://graph.microsoft.com/beta/$metadata#security/attackSimulation/payloads/2f5548d1-0dd8-4cc8-9de0-e0d6ec7ea3dc",
  "id": "2f5548d1-0dd8-4cc8-9de0-e0d6ec7ea3dc",
  "name": "AttackSimTest Payload",
  "description": "AttackSim Test Payload",
  "simulationAttackType": "social",
  "platform": "email",
  "isAutomated": null,
  "status": "draft",
  "source": "tenant",
  "language": "en",
  "predictedCompromiseRate": 20.0,
  "complexity": "medium",
  "technique": "credentialHarvesting",
  "createdBy": {
    "email": "faiza@contoso.com",
    "id": "121212",
    "displayName": "Faiza"
  },
  "createdDateTime": "2022-01-12T03:15:01.5906699Z",
  "lastModifiedBy": {
    "email": "faiza@contoso.com",
    "id": "121212",
    "displayName": "Faiza"
  },
  "lastModifiedDateTime": "2021-10-07T12:23:18.8157586Z",
  "theme": "personalizedOffer",
  "brand": "microsoft",
  "industry": "IT",
  "isCurrentEvent": false,
  "isControversial": false,
  "detail": null,
  "payloadTags": []
}
```
