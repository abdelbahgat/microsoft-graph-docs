---
title: "List recoveryKeys"
description: "Get a list of the bitlockerRecoveryKey objects and their properties."
author: "hafowler"
ms.localizationpriority: medium
ms.prod: "directory-management"
doc_type: apiPageType
---

# List recoveryKeys

Namespace: microsoft.graph

Get a list of the [bitlockerRecoveryKey](../resources/bitlockerrecoverykey.md) objects and their properties. 

This operation does not return the **key** property. For information about how to read the **key** property, see [Get bitlockerRecoveryKey](bitlockerrecoverykey-get.md).

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from most to least privileged)|
|:---|:---|
|Delegated (work or school account)|BitLockerKey.ReadBasic.All, BitLockerKey.Read.All|
|Delegated (personal Microsoft account)|Not supported|
|Application|Not supported|

For delegated permissions, the calling user must be the registered owner of the device that the BitLocker recovery key was originally backed up from, or they must be in one of the following [directory roles](/azure/active-directory/roles/permissions-reference):

* Global administrator
* Cloud device administrator
* Helpdesk administrator
* Intune service administrator
* Security administrator
* Security reader
* Global reader

## HTTP request

To get a list of BitLocker keys within the tenant:

<!-- {
  "blockType": "ignored"
}
-->

``` http
GET /informationProtection/bitlocker/recoveryKeys
```

## Optional query parameters

This method supports the `$filter` OData query parameter to filter results by the **deviceId** of the device that the key was most recently backed up to. This method does not support `$top`. For general information, see [OData query parameters](/graph/query-parameters).

The response might also contain an `odata.nextLink`, which you can use to page through the result set. For details, see [Paging Microsoft Graph data](/graph/paging).

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

If successful, this method returns a `200 OK` response code and a collection of [bitlockerRecoveryKey](../resources/bitlockerrecoverykey.md) objects in the response body.

## Examples

### Example 1: Retrieve a list of BitLocker keys in the tenant.

#### Request

The following is an example of the request.


<!-- {
  "blockType": "request",
  "name": "list_bitlockerrecoverykey"
}
-->
``` http
GET https://graph.microsoft.com/v1.0/informationProtection/bitlocker/recoveryKeys
User-Agent: "Dsreg/10.0 (Windows 10.0.19043.1466)"
ocp-client-name: "My Friendly Client"
ocp-client-version: "1.2"
```


#### Response

The following is an example of the response.

>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.bitlockerRecoveryKey)"
}
-->

``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#microsoft.graph.bitlockerRecoveryKey",
      "id": "b465e4e8-e4e8-b465-e8e4-65b4e8e465b4",
      "createdDateTime": "2020-06-15T13:45:30.0000000Z",
      "volumeType": "1",
      "deviceId": "2ef04ef1-23b0-2e00-a3a5-ab345e567ab6"
    },
    {
      "@odata.type": "#microsoft.graph.bitlockerRecoveryKey",
      "id": "6a30ed7b-247b-4d26-86b5-2f405e55ea42",
      "createdDateTime": "2020-06-15T13:45:30.0000000Z",
      "volumeType": "1",
      "deviceId": "1ab40ab2-32a8-4b00-b6b5-ba724e407de9"
    }
  ]
}
```

### Example 2: Retrieve a list of BitLocker keys filtered by deviceId.

#### Request

The following is an example of the request.



<!-- {
  "blockType": "request",
  "name": "list_bitlockerrecoverykey_filter_deviceId"
}
-->
``` http
GET https://graph.microsoft.com/v1.0/informationProtection/bitlocker/recoveryKeys?$filter=deviceId eq '1ab40ab2-32a8-4b00-b6b5-ba724e407de9'
User-Agent: "Dsreg/10.0 (Windows 10.0.19043.1466)"
ocp-client-name: "My Friendly Client"
ocp-client-version: "1.2"
```


#### Response

The following is an example of the response.

>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.bitlockerRecoveryKey)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#microsoft.graph.bitlockerRecoveryKey",
      "id": "b465e4e8-e4e8-b465-e8e4-65b4e8e465b4",
      "createdDateTime": "2020-06-15T13:45:30.0000000Z",
      "volumeType": "1",
      "deviceId": "1ab40ab2-32a8-4b00-b6b5-ba724e407de9"
    }
  ]
}
```
