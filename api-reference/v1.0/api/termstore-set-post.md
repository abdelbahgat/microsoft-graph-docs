---
title: "Create set"
description: "Create a new set object."
author: vishriv
ms.localizationpriority: medium
ms.prod: sites-and-lists
doc_type: apiPageType
---

# Create set
Namespace: microsoft.graph.termStore

Create a new [set](../resources/termstore-set.md) object.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account) |TermStore.ReadWrite.All |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | Not supported. |


## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
POST sites/{site-id}/termStore/sets
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply a JSON representation of the [set](../resources/termstore-set.md) object.

The following table shows the properties that are required when you create the [set](../resources/termstore-set.md) object.

|Property|Type|Description|
|:---|:---|:---|
|localizedNames|[microsoft.graph.termstore.localizedName](../resources/termstore-localizedname.md) collection|Name of the set to be created.|
|parentGroup|[microsoft.graph.termstore.group](../resources/termstore-group.md)|termstore-group under which the set needs to be created.|



## Response

If successful, this method returns a `201 Created` response code and a [microsoft.graph.termStore.set](../resources/termstore-set.md) object in the response body.

## Examples

### Request
``` http
POST https://graph.microsoft.com/v1.0/sites/microsoft.sharepoint.com,b9b0bc03-cbc4-40d2-aba9-2c9dd9821ddf,6a742cee-9216-4db5-8046-13a595684e74/termStore/sets
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.termStore.set",
  "parentGroup":{
      "id": "fc733b51-10f1-40fd-b784-dc6d1e42804b"
   },
   "localizedNames" : [
      {
        "languageTag" : "en-US",
        "name" : "Department"
      }
  ]
}
```


### Response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.termstore.set"
}
-->
``` http
HTTP/1.1 201 Created
Content-Type: application/json
{
  "@odata.type": "#microsoft.graph.termStore.set",
  "id": "3607e9f9-e9f9-3607-f9e9-0736f9e90736",
  "localizedNames" : [
      {
        "languageTag" : "en-US",
        "name" : "Department"
      }
  ]
}
```


[microsoft.graph.termStore.set]: ../resources/termstore-set.md
[microsoft.graph.termStore.group]: ../resources/termstore-group.md
[microsoft.graph.termStore.term]: ../resources/termstore-term.md

<!--
{
  "type": "#page.annotation",
  "description": "Create a termSet entity in termStore",
  "keywords": "term,termStore",
  "section": "documentation",
  "tocPath": "termStore/Create termSet",
  "suppressions": [
  ]
}
-->


