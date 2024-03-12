---
title: "ediscoveryReviewSet: export"
description: "Initiate an export from a reviewSet."
author: "SeunginLyu"
ms.localizationpriority: medium
ms.prod: "ediscovery"
doc_type: "apiPageType"
---

# ediscoveryReviewSet: export
Namespace: microsoft.graph.security

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Initiate an export from a **reviewSet**.  For details, see [Export documents from a review set in eDiscovery (Premium)](/microsoft-365/compliance/export-documents-from-review-set).


## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|eDiscovery.Read.All, eDiscovery.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|Not supported.|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /security/cases/ediscoveryCases/{ediscoveryCaseId}/reviewSets/{ediscoveryReviewSetId}/export
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply a JSON representation of the parameters.

The following table shows the parameters that can be used with this action.

|Parameter|Type|Description|
|:---|:---|:---|
|description|String| Description of the export. |
|exportOptions|String|Specifies options that control the format of the export. Possible values are: `originalFiles`, `text`, `pdfReplacement`, `fileInfo`, `tags`. The `fileInfo` member is deprecated and will stop returning data on April 30th, 2023. Going forward, the summary and load file are always included.|
|exportStructure|String| Options that control file structure and packaging of the export. Possible values are: `none`, `directory`, `pst`.|
|outputName|String| Name of the export. Required. |
|azureBlobContainer (deprecated)|String| When you export to your own Azure storage account, this is the container URL. The **azureBlobContainer** property is deprecated and will stop returning data on April 30th, 2023. |
|azureBlobToken (deprecated)|String| When you export to your own Azure storage account, SAS token for the container URL. The **azureBlobToken** property is deprecated and will stop returning data on April 30th, 2023. |

## Response

If the export has started successfully, this action returns a `202 Accepted` response code. The response will also contain a `Location` header, which contains the location of the [Export operation](../resources/security-ediscoveryexportoperation.md) that was created to handle the export.

## Examples

### Request
The following is an example of a request.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "ediscoveryreviewsetthis.export"
}
-->
``` http
POST https://graph.microsoft.com/beta/security/cases/ediscoveryCases/58399dff-cebe-478f-b1af-d3227f1fd645/reviewSets/273f11a1-17aa-419c-981d-ff10d33e420f/export
Content-Type: application/json

{
    "outputName": "Export via API",
    "description": "Export for the Contoso investigation",
    "exportOptions": "originalFiles,fileInfo,tags",
    "exportStructure": "directory"
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/ediscoveryreviewsetthisexport-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/ediscoveryreviewsetthisexport-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/ediscoveryreviewsetthisexport-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/ediscoveryreviewsetthisexport-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/ediscoveryreviewsetthisexport-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response
The following is an example of the response.

<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 202 Accepted
```

