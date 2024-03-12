---
title: "List calendars"
description: "Retrieve a list of calendars belonging to a calendar group."
author: "iamgirishck"
ms.localizationpriority: medium
ms.prod: "outlook"
doc_type: apiPageType
---

# List calendars

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Retrieve a list of calendars belonging to a calendar group.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
| :------------------------------------- | :------------------------------------------ |
| Delegated (work or school account)     | Calendars.ReadBasic, Calendars.Read         |
| Delegated (personal Microsoft account) | Calendars.ReadBasic, Calendars.Read         |
| Application                            | Calendars.ReadBasic, Calendars.Read         |

## HTTP request

<!-- { "blockType": "ignored" } -->

A user's default [calendarGroup](../resources/calendargroup.md).

```http
GET /me/calendars
GET /users/{id | userPrincipalName}/calendars
```

Any [calendarGroup](../resources/calendargroup.md) of a user.

```http
GET /me/calendarGroups/{id}/calendars
GET /users/{id | userPrincipalName}/calendarGroups/{id}/calendars
```

## Optional query parameters

This method supports the [OData Query Parameters](/graph/query-parameters) to help customize the response.

## Request headers

| Name          | Type   | Description               |
| :------------ | :----- | :------------------------ |
| Authorization | string | Bearer {token}. Required. |

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and collection of [Calendar](../resources/calendar.md) objects in the response body.

## Example

##### Request

Here is an example of the request.


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "calendargroup_get_calendars"
}-->

```msgraph-interactive
GET https://graph.microsoft.com/beta/me/calendarGroups/{id}/calendars
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/calendargroup-get-calendars-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/calendargroup-get-calendars-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/calendargroup-get-calendars-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/calendargroup-get-calendars-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/calendargroup-get-calendars-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/calendargroup-get-calendars-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

##### Response

Here is an example of the response. Note: The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.calendar",
  "isCollection": true
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "value": [
    {
      "name": "name-value",
      "color": {
      },
      "calendarGroupId":"calendarGroupId-value",
      "changeKey": "changeKey-value",
      "id": "id-value"      
    }
  ]
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->

<!--
{
  "type": "#page.annotation",
  "description": "List calendars",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->
