---
title: "Get remoteDesktopSecurityConfiguration"
description: "Read the properties and relationships of a remoteDesktopSecurityConfiguration object on a servicePrincipal."
author: "SanDeo-MSFT"
ms.localizationpriority: medium
ms.prod: "applications"
doc_type: apiPageType
---

# Get remoteDesktopSecurityConfiguration
Namespace: microsoft.graph

Read the properties and relationships of a [remoteDesktopSecurityConfiguration](../resources/remotedesktopsecurityconfiguration.md) object on a servicePrincipal. Use this configuration to view the Microsoft Entra ID [Remote Desktop Services (RDS) authentication protocol](/openspecs/windows_protocols/ms-rdpbcgr/dc43f040-d75d-49a9-90c6-0c9999281136) to authenticate a user to [Microsoft Entra joined](/azure/active-directory/devices/concept-directory-join) or [Microsoft Entra hybrid joined](/azure/active-directory/devices/concept-hybrid-join) devices. Additionally you can view any targetDeviceGroups that have been configured for SSO.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account) | Application.Read.All, Directory.Read.All, Application-RemoteDesktopConfig.ReadWrite.All, Application.ReadWrite.All, Directory.ReadWrite.All|
|Delegated (personal Microsoft account) | Not supported.|
|Application | Application.Read.All, Directory.Read.All, Application-RemoteDesktopConfig.ReadWrite.All, Application.ReadWrite.OwnedBy, Application.ReadWrite.All, Directory.ReadWrite.All|

[!INCLUDE [rbac-remote-desktop-security-config-apis](../includes/rbac-for-apis/rbac-remote-desktop-security-config-apis.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /servicePrincipals/{servicePrincipalsId}/remoteDesktopSecurityConfiguration
```

## Optional query parameters
This method doesn't support any OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a [remoteDesktopSecurityConfiguration](../resources/remotedesktopsecurityconfiguration.md) object in the response body.

## Examples

### Request
The following example shows a request.
# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "get_remotedesktopsecurityconfiguration"
}
-->
``` http
GET https://graph.microsoft.com/v1.0/servicePrincipals/00af5dfb-85da-4b41-a677-0c6b86dd34f8/remoteDesktopSecurityConfiguration
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/get-remotedesktopsecurityconfiguration-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/get-remotedesktopsecurityconfiguration-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/get-remotedesktopsecurityconfiguration-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-remotedesktopsecurityconfiguration-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-remotedesktopsecurityconfiguration-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/get-remotedesktopsecurityconfiguration-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/get-remotedesktopsecurityconfiguration-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/get-remotedesktopsecurityconfiguration-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response
The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.remoteDesktopSecurityConfiguration"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": {
    "@odata.type": "#microsoft.graph.remoteDesktopSecurityConfiguration",
    "id": "ca738153-c98a-f822-a7d1-5a6e1058462b",
    "isRemoteDesktopProtocolEnabled": true,
    "targetDeviceGroups": [
      {
        "id": "1a9db3ab-0acf-4808-99ae-e8ed581cb2e0",
        "displayName": "Device Group A"
      }
    ]
  }
}
```
