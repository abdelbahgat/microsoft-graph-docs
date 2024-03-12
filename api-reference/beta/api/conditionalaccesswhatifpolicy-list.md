---
title: "List conditionalAccessWhatIfPolicy objects"
description: "Get a list of the conditionalAccessWhatIfPolicy objects and their properties."
author: "**TODO: Provide GitHub Name. See [topic-level metadata reference](https://aka.ms/msgo?pagePath=Document-APIs/Guidelines/Metadata)**"
ms.localizationpriority: medium
ms.subservice: "**TODO: Add MS prod. See [topic-level metadata reference](https://aka.ms/msgo?pagePath=Document-APIs/Guidelines/Metadata)**"
doc_type: apiPageType
---

# List conditionalAccessWhatIfPolicy objects

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a list of the [conditionalAccessWhatIfPolicy](../resources/conditionalaccesswhatifpolicy.md) objects and their properties.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "conditionalaccesswhatifpolicy-list-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/conditionalaccesswhatifpolicy-list-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET ** Collection URI for microsoft.graph.conditionalAccessWhatIfPolicy not found
```

## Optional query parameters

This method supports some of the OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [conditionalAccessWhatIfPolicy](../resources/conditionalaccesswhatifpolicy.md) objects in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "list_conditionalaccesswhatifpolicy"
}
-->
``` http
GET https://graph.microsoft.com/beta** Collection URI for microsoft.graph.conditionalAccessWhatIfPolicy not found
```


### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.conditionalAccessWhatIfPolicy)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
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
  ]
}
```

