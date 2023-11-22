---
author: spgraph-docs-team
description: "Track changes in a drive item and its children over time."
ms.date: 09/10/2017
title: "driveItem: delta"
ms.localizationpriority: medium
ms.prod: "sharepoint"
doc_type: apiPageType
---
# driveItem: delta

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Track changes in a [driveItem](../resources/driveitem.md) and its children over time.

Your app begins by calling `delta` without any parameters.
The service starts enumerating the drive's hierarchy, returning pages of items and either an `@odata.nextLink` or an `@odata.deltaLink`, as described below.
Your app should continue calling with the `@odata.nextLink` until you no longer see an `@odata.nextLink` returned, or you see a response with an empty set of changes.

After you have finished receiving all the changes, you may apply them to your local state.
To check for changes in the future, call `delta` again with the `@odata.deltaLink` from the previous response.

Deleted items are returned with the [`deleted` facet](../resources/deleted.md).
Items with this property set should be removed from your local state.

**Note:** you should only delete a folder locally if it's empty after syncing all the changes.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "driveitem_delta" } -->
[!INCLUDE [permissions-table](../includes/permissions/driveitem-delta-permissions.md)]

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
GET /drives/{drive-id}/root/delta
GET /groups/{groupId}/drive/root/delta
GET /me/drive/root/delta
GET /sites/{siteId}/drive/root/delta
GET /users/{userId}/drive/root/delta
```

## Function parameters

| Parameter   | Type  | Description                                                                                                                          |
|:-------|:-------|:-------------------------------------------------------------------------------------------------------------------------------------|
| token  | string | Optional. If unspecified, enumerates the hierarchy's current state. If `latest`, returns empty response with latest delta token. If a previous delta token, returns new state since that token.

## Optional query parameters

This method supports the `$select`, `$expand`, and `$top` [OData query parameters](/graph/query-parameters) to customize the response.

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [DriveItem](../resources/driveitem.md) resources in the response body.

In addition to the collection of DriveItems, the response will also include one of the following properties:

| Name                 | Value  | Description                                                                                                                                      |
|:---------------------|:-------|:-------------------------------------------------------------------------------------------------------------------------------------------------|
| **@odata.nextLink**  | url    | A URL to retrieve the next available page of changes, if there are more changes in the current set.                                        |
| **@odata.deltaLink** | url    | A URL returned instead of **@odata.nextLink** after all current changes have been returned. Used to read the next set of changes in the future.  |

## Examples

### Example 1: Initial request

Here's an example of how to call this API to establish your local state.

#### Request

Here's an example of the initial request.


# [HTTP](#tab/http)
<!-- { "blockType": "request", "name": "get_item_delta_first" } -->

```msgraph-interactive
GET https://graph.microsoft.com/beta/me/drive/root/delta
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/get-item-delta-first-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/get-item-delta-first-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/get-item-delta-first-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-item-delta-first-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-item-delta-first-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/get-item-delta-first-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/get-item-delta-first-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/get-item-delta-first-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response

Here's an example of the response.

<!-- { "blockType": "response", "@odata.type": "Collection(microsoft.graph.driveItem)", "truncated": true, "scope": "file.read" } -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
    "value": [
        {
            "id": "0123456789abc",
            "name": "folder2",
            "folder": { }
        },
        {
            "id": "123010204abac",
            "name": "file.txt",
            "file": { }
        },
        {
            "id": "2353010204ddgg",
            "name": "file5.txt",
            "deleted": { }
        }
    ],
    "@odata.nextLink": "https://graph.microsoft.com/v1.0/me/drive/delta(token=1230919asd190410jlka)"
}
```

This response includes the first page of changes, and the **@odata.nextLink** property indicates that there are more items available in the current set of items.
Your app should continue to request the URL value of **@odata.nextLink** until all pages of items have been retrieved.

### Example 2: Last page in a set

Here's an example of how to call this API to update your local state.

#### Request

Here's an example request after the initial request.


# [HTTP](#tab/http)
<!-- { "blockType": "request", "name": "get_item_delta_last" }-->

```msgraph-interactive
GET https://graph.microsoft.com/beta/me/drive/root/delta(token='1230919asd190410jlka')
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/get-item-delta-last-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/get-item-delta-last-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/get-item-delta-last-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-item-delta-last-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-item-delta-last-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/get-item-delta-last-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [snippet-not-available](../includes/snippets/snippet-not-available.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/get-item-delta-last-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response

Here's an example of the response.

<!-- { "blockType": "response", "truncated": true, "@odata.type": "Collection(microsoft.graph.driveItem)", "scope": "file.read" } -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
    "value": [
        {
            "id": "0123456789abc",
            "name": "folder2",
            "folder": { },
            "deleted": { }
        },
        {
            "id": "123010204abac",
            "name": "file.txt",
            "file": { }
        }
    ],
    "@odata.deltaLink": "https://graph.microsoft.com/v1.0/me/drive/root/delta?(token='1230919asd190410jlka')"
}
```

This response indicates that the item named `folder2` was deleted and the item `file.txt` was either added or modified between the initial request and this request to update the local state.

The final page of items includes the **@odata.deltaLink** property, which provides the URL that can be used later to retrieve changes since the current set of items.

There may be cases when the service can't provide a list of changes for a given token (for example, if a client tries to reuse an old token after being disconnected for a long time, or if server state has changed and a new token is required).
In these cases the service returns an `HTTP 410 Gone` error with an error response containing one of the error codes below, and a `Location` header containing a new nextLink that starts a fresh delta enumeration from scratch.
After finishing the full enumeration, compare the returned items with your local state and follow these instructions.

| Error Type                       | Instructions                                                                                                                                                                                                                    |
|:---------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `resyncChangesApplyDifferences`  | Replace any local items with the server's version (including deletes) if you're sure that the service was up to date with your local changes when you last synched. Upload any local changes that the server doesn't know about. |
| `resyncChangesUploadDifferences` | Upload any local items that the service didn't return, and upload any files that differ from the server's version (keeping both copies if you're not sure which one is more up-to-date).                                       |

### Example 3: Retrieving the current deltaLink

In some scenarios, it may be useful to request the current deltaLink value without first enumerating all of the items in the drive already.

This can be useful if your app only wants to know about changes, and doesn't need to know about existing items.
To retrieve the latest deltaLink, call `delta` with a query string parameter `?token=latest`.

> **Note:** If you are trying to maintain a full local representation of the items in a folder or a drive, you must use `delta` for the initial enumeration.
Other approaches, such as paging through the `children` collection of a folder, are not guaranteed to return every single item if any writes take place during the enumeration.
Using `delta` is the only way to guarantee that you've read all of the data you need to.

#### Request

# [HTTP](#tab/http)
<!-- { "blockType": "request", "name": "get-delta-with_latest_token", "scope": "files.read", "target": "action" } -->

```msgraph-interactive
GET /me/drive/root/delta?token=latest
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/get-delta-with-latest-token-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/get-delta-with-latest-token-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/get-delta-with-latest-token-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-delta-with-latest-token-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-delta-with-latest-token-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/get-delta-with-latest-token-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/get-delta-with-latest-token-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/get-delta-with-latest-token-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response

<!-- { "blockType": "response", "@odata.type": "Collection(microsoft.graph.driveItem)" } -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
    "value": [ ],
    "@odata.deltaLink": "https://graph.microsoft.com/v1.0/me/drive/root/delta?token=1230919asd190410jlka"
}
```

### Example 4: Retrieving delta results using a timestamp

In some scenarios, the client may know the state of a drive up to a specific time, but not have a deltaLink for that point in time. In this case, the client can call `delta` using a URL encoded timestamp for the value of the `token` query string parameter, for example, `?token=2021-09-29T20%3A00%3A00Z` or '?token=2021-09-29T12%3A00%3A00%2B8%3A00'.

Using a timestamp in place of a token is only supported on OneDrive for Business and SharePoint.

> **Note:** Clients should use the deltaLink provided by `delta` queries when possible, rather than generating their own token. This capability should only be utilized when the deltaLink is not known.


#### Request


# [HTTP](#tab/http)
<!-- { "blockType": "request", "name": "get-delta-timestamp", "scopes": "files.read", "tags": "service.graph", "target": "action" } -->

```msgraph-interactive
GET /me/drive/root/delta?token=2021-09-29T20%3A00%3A00Z
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/get-delta-timestamp-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/get-delta-timestamp-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/get-delta-timestamp-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-delta-timestamp-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-delta-timestamp-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/get-delta-timestamp-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/get-delta-timestamp-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/get-delta-timestamp-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response

<!-- { "blockType": "response", "truncated": true, "@odata.type": "Collection(microsoft.graph.driveItem)", "scope": "file.read" } -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
    "value": [
        {
            "id": "0123456789abc",
            "name": "folder2",
            "folder": { },
            "deleted": { }
        },
        {
            "id": "123010204abac",
            "name": "file.txt",
            "file": { }
        }
    ],
    "@odata.deltaLink": "https://graph.microsoft.com/v1.0/me/drive/root/delta?(token='1230919asd190410jlka')"
}
```

## Remarks

* The delta feed shows the latest state for each item, not each change. If an item were renamed twice, it would only show up once, with its latest name.
* The same item may appear more than once in a delta feed, for various reasons. You should use the last occurrence you see.
* The `parentReference` property on items won't include a value for **path**. This occurs because renaming a folder doesn't result in any descendants of the folder being returned from **delta**. **When using delta you should always track items by id**.
* Delta query won't return some DriveItem properties, depending on the operation and service type, as shown in the following tables.

    **OneDrive for Business**

    | Operation type | Properties omitted by delta query |
    |---------|----------|
    | Create/Modify | `ctag` |
    | Delete | `ctag`, `name` |


    **OneDrive (consumer)**

    | Operation type | Properties omitted by delta query |
    |---------|----------|
    | Create/Modify | n/a |
    | Delete | `ctag`, `size` |

## Scanning permissions hierarchies

By default, the delta query response includes sharing information for all items in the query that changed even if they inherit their permissions from their parent and didn't have direct sharing changes themselves. This typically then results in a follow-up call to get the permission details for every item rather than just the ones whose sharing information changed. You can optimize your understanding of how permission changes happen by adding the `Prefer: hierarchicalsharing` header to your delta query request.

When the `Prefer: hierarchicalsharing` header is provided, sharing information is returned for the root of the permissions hierarchy, and items that explicitly have sharing changes. In cases where the sharing change is to remove sharing from an item, you find an empty sharing facet to differentiate between items that inherit from their parent and those that are unique but have no sharing links. You'll also see this empty sharing facet on the root of a permission hierarchy that isn't shared to establish the initial scope.

In many scanning scenarios, you might be interested specifically in changes to permissions. To make it clear in the delta query response which changes are the result of permissions being changed, you can provide the `Prefer: deltashowsharingchanges` header. When this header is provided, all items that appear in the delta query response due to permission changes have the `@microsoft.graph.sharedChanged":"True"` OData annotation. This feature is applicable to SharePoint and OneDrive for Business but not consumer OneDrive accounts.

> [!NOTE]
> * The use of `Prefer: deltashowsharingchanges` header requires you to use `Prefer: deltashowremovedasdeleted` and `Prefer: deltatraversepermissiongaps`. These header values can be joined together in a single header: `Prefer: deltashowremovedasdeleted, deltatraversepermissiongaps, deltashowsharingchanges`.
>
> * In order to process permissions correctly your application will need to request **Sites.FullControl.All** permissions.

For more information about scanning scenarios, see [Best practices for discovering files and detecting changes at scale](/onedrive/developer/rest-api/concepts/scan-guidance).

## Error responses

In addition to the resync errors detailed above, see [Error Responses][error-response] for details about how errors are returned.

## See also
[Use delta query to track changes in Microsoft Graph data](/graph/delta-query-overview)
[Best practices for discovering files and detecting changes at scale](/onedrive/developer/rest-api/concepts/scan-guidance)

[error-response]: /graph/errors
[item-resource]: ../resources/driveitem.md

<!--
{
  "type": "#page.annotation",
  "description": "Sync changes from the service to your client state.",
  "keywords": "sync,delta,changes,$delta",
  "section": "documentation",
  "tocPath": "Items/Sync changes",
  "suppressions": [
  ]
}
-->


