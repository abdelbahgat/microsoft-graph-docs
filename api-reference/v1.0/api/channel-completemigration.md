---
title: "channel: completeMigration"
description: "Complete the migration of external messages by removing migration mode from a channel."
ms.localizationpriority: medium
author: "RamjotSingh"
ms.prod: "microsoft-teams"
doc_type: apiPageType
---

# channel: completeMigration

Namespace: microsoft.graph

Complete the message migration process by removing `migration mode` from a [channel](../resources/channel.md) in a team. `Migration mode` is a special state that prevents certain operations, like sending messages and adding members, during the data migration process.

After a **completeMigration** request is made, you cannot import additional messages into the team. You can add members to the team after the request returns a successful response.

## Permissions

The following permission is required to call this API. To learn more, *see* [Permissions](/graph/permissions-reference).

|Permission type      | Permission  |
|:--------------------|:---------------------------------------------------------|
| Delegated (work or school account)  | Not supported.|
| Delegated (personal Microsoft account) | Not supported. |
|Application | Teamwork.Migrate.All|

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /teams/{team-id}/channels/{channel-id}/completeMigration
```

## Request headers

| Header       | Value |
|:---------------|:--------|
| Authorization  | Bearer {token}. Required.  |

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `204 No Content` response code. It does not return anything in the response body.

## Example

### Request

The following is an example of the request.
<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD022 -->



# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "completeMigration_channel"
}-->

```http
POST https://graph.microsoft.com/v1.0/teams/57fb72d0-d811-46f4-8947-305e6072eaa5/channels/19:4b6bed8d24574f6a9e436813cb2617d8@thread.tacv2/completeMigration
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/completemigration-channel-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/completemigration-channel-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/completemigration-channel-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/completemigration-channel-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/completemigration-channel-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/completemigration-channel-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---


<!-- markdownlint-disable MD001 -->
<!-- markdownlint-disable MD024 -->
### Response

The following is an example of the response.
<!-- {
  "blockType": "response",
  "truncated": true
} -->

```http
HTTP/1.1 204 No Content
```

<!-- uuid: 5793eec6-0e5a-11eb-adc1-0242ac120002
2020-10-14 20:22:11 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "completeMigration_ channel",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->
