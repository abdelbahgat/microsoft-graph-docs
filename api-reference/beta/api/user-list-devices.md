---
title: "List user devices (deprecated)"
description: "Get a list of user devices that support Project Rome capabilities. This includes the ability to launch an app, or message or send data to an application. After you do a GET call on me/devices, pass in the ID of the device to send a command to your device."
ms.localizationpriority: medium
author: "jpettere"
ms.prod: "users"
doc_type: apiPageType
---

# List user devices (deprecated)

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

> [!CAUTION]
> This API is deprecated and stopped returning data on September 30, 2020.

Get a list of user devices that support Project Rome capabilities. This includes the ability to launch an app, or message or send data to an application. After you do a GET call on me/devices, pass in the ID of the device to [send a command](send-device-command.md) to your device.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).


|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Not supported.    |
|Delegated (personal Microsoft account) | Device.Read    |
|Application | Not supported. |

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
GET me/devices
```

## Request headers

| Header |Value
|:----|:------|
|Authorization| Bearer {token}. Required. |
|Accept | application/json |

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a 200 response code and the user device properties in the response body.

<!-- { "blockType": "ignored" } -->

```http
HTTP/1.1 200 OK
```

<!-- { "blockType": "ignored" } -->

```json
{
  "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#devices",
  "value": [
    {
      "name": "name",
      "id": "id",
      "status": "status",
      "platform": "platform",
      "kind": "formFactor",
      "model": "model",
      "manufacturer": "manufacturer",
    }
  ]
}
```

## Example
This example will return the list of devices for a user. To command a device using `me/devices/{id}/command`, you will need to get the ID of the device that is returned.

#### Request

The following is an example of the request.

<!-- {
  "blockType": "ignored",
  "name": "list_devices"
}-->

```http
GET me/devices
Authorization: Bearer Eaeou....
Content-Type: application/json; charset=utf-8
```

#### Response

The following is an example of the response. Note: The response object shown here might be shortened for readability.

<!-- {
  "blockType": "ignored",
  "truncated": true,
  "@odata.type": "microsoft.graph.device",
  "isCollection": true
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "value": [
    {
      "Name": "JimSurface",
      "id": "6841b3db-2b55-467b-ad84-79a41a4ef665",
      "Manufacturer": "Microsoft Corporation",
      "Model": "Surface Book",
      "Kind": "Tablet",
      "Status": "Unknown",
      "Platform": "Windows"
    }
  ]
}
```


