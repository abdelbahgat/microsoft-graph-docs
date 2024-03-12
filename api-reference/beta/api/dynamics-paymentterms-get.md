---
title: "Get paymentTerms" 
description: "Retrieve the properties and relationships of a paymentTerms object for Dynamics 365 Business Central."
services: "project-madeira"
documentationcenter: ""
author: "SusanneWindfeldPedersen"
ms.localizationpriority: medium
ms.prod: "dynamics-365-business-central"
doc_type: apiPageType
---

# Get paymentTerms

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Retrieve the properties and relationships of a [paymentTerms](../resources/dynamics-paymentterms.md) object for Dynamics 365 Business Central.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type |Permissions (from least to most privileged)|
|:---------------|:------------------------------------------|
|Delegated (work or school account)|Financials.ReadWrite.All |
|Delegated (personal Microsoft account|Not supported.|
|Application|Financials.ReadWrite.All|

## HTTP request

```
GET /financials/companies/{id}/paymentTerms/{id}
```

## Optional query parameters
This method supports the [OData query parameters](/graph/query-parameters) to help customize the response.

## Request headers
|Header         |Value                     |
|---------------|--------------------------|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a `200 OK` response code and a **paymentTerms** object in the response body.

## Examples

### Request

The following is an example of the request.
```http
GET https://graph.microsoft.com/beta/financials/companies/{id}/paymentTerms/{id}
```

### Response

The following is an example of the response. 

> **Note**: The response object shown here might be shortened for readability.

```json
{
  "id": "id-value",
  "code": "7 DAYS",
  "displayName": "Net 7 days",
  "dueDateCalculation": "7D",
  "discountDateCalculation": "",
  "discountPercent": 0,
  "calculateDiscountOnCreditMemos": false,
  "lastModifiedDateTime": "2017-03-15T02:20:55.203Z"
}
```


