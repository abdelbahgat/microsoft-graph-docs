---
title: "Get bitlockerRecoveryKey"
description: "Retrieve the properties and relationships of a bitlockerRecoveryKey object."
author: "hafowler"
ms.localizationpriority: medium
ms.prod: "directory-management"
doc_type: apiPageType
---

# Get bitlockerRecoveryKey
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Retrieve the properties and relationships of a [bitlockerRecoveryKey](../resources/bitlockerrecoverykey.md) object. 

By default, this operation does not return the **key** property that represents the actual recovery key. To include the **key** property in the response, use the `$select` OData query parameter. Including the `$select` query parameter triggers an Azure AD audit of the operation and generates an audit log. You can find the log in [Azure AD audit logs](/azure/active-directory/reports-monitoring/concept-audit-logs) under the KeyManagement category.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from most to least privileged)|
|:---|:---|
|Delegated (work or school account)|BitLockerKey.ReadBasic.All, BitLockerKey.Read.All|
|Delegated (personal Microsoft account)|Not supported|
|Application|Not supported|

>**Note:** For delegated permissions to allow apps to get BitLockerRecoveryKey resources on behalf of the signed-in user, the tenant administrator must have assigned the user one of the following roles, or the user must be the **registered owner** of the device that the BitLocker key was originally backed up from: 
* Global administrator
* Cloud device administrator
* Helpdesk administrator
* Intune service administrator
* Security administrator
* Security reader
* Global reader

## HTTP request
To get the specified BitLocker key without returning the **key** property:
<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /informationProtection/bitlocker/recoveryKeys/{bitlockeryRecoveryKeyId}
```

To get the specified BitLocker key including its **key** property:
<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /informationProtection/bitlocker/recoveryKeys/{bitlockeryRecoveryKeyId}?$select=key
```

## Optional query parameters
This method supports the `$select` OData query parameter to return the **key** property. For details, see [Example 2](#example-2). For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|User-Agent|The identifier for the calling application. This value contains information about the operating system and the browser used. Required.|
|ocp-client-name|The name of the client application performing the API call. This header is used for debugging purposes. Optional.|
|ocp-client-version|The version of the client application performing the API call. This header is used for debugging purposes. Optional.|


## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a [bitlockerRecoveryKey](../resources/bitlockerrecoverykey.md) object in the response body.

## Examples

### Example 1
Get the BitLocker key by specifying the **key id**. This example does not return the **key** property.

#### Request
The following is an example of the request.

<!-- {
  "blockType": "request",
  "sampleKeys": ["b465e4e8-e4e8-b465-e8e4-65b4e8e465b4"],
  "name": "get_bitlockerrecoverykey_3"
}
-->
``` http
GET https://graph.microsoft.com/beta/informationProtection/bitlocker/recoveryKeys/b465e4e8-e4e8-b465-e8e4-65b4e8e465b4
User-Agent: "Dsreg/10.0 (Windows 10.0.19043.1466)"
ocp-client-name: "My Friendly Client"
ocp-client-version: "1.2"
```



#### Response
The following is an example of the response.

**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.bitlockerRecoveryKey"
}
-->
``` http
HTTP/1.1 200 OK
Content-type: application/json

{
  "value": {
    "@odata.type": "#microsoft.graph.bitlockerRecoveryKey",
    "id": "b465e4e8-e4e8-b465-e8e4-65b4e8e465b4",
    "createdDateTime": "2020-06-15T13:45:30.0000000Z",
    "volumeType": 1,
    "deviceId": "1ab40ab2-32a8-4b00-b6b5-ba724e407de9"
  }
}
```

### Example 2
Get the BitLocker key with the **key** property by specifying the **key id**.

#### Request
The following is an example of the request.

<!-- {
  "blockType": "request",
  "sampleKeys": ["b465e4e8-e4e8-b465-e8e4-65b4e8e465b4"],
  "name": "get_bitlockerrecoverykey_4"
}
-->
``` http
GET https://graph.microsoft.com/beta/informationProtection/bitlocker/recoveryKeys/b465e4e8-e4e8-b465-e8e4-65b4e8e465b4?$select=key
User-Agent: "Dsreg/10.0 (Windows 10.0.19043.1466)"
ocp-client-name: "My Friendly Client"
ocp-client-version: "1.2"
```



#### Response
The following is an example of the response.

**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.bitlockerRecoveryKey"
}
-->
``` http
HTTP/1.1 200 OK
Content-type: application/json

{
  "value": {
    "@odata.type": "#microsoft.graph.bitlockerRecoveryKey",
    "id": "b465e4e8-e4e8-b465-e8e4-65b4e8e465b4",
    "createdDateTime": "String (timestamp)",
    "volumeType": 1,
    "deviceId": "1ab40ab2-32a8-4b00-b6b5-ba724e407de9",
    "key": "123456-231453-873456-213546-654678-765689-123456-324565"
  }
}
```
