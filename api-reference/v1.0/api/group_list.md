# List groups

Retrieve a list of group objects.
### Prerequisites
One of the following **scopes** is required to execute this API: *Group.Read.All* or *Group.ReadWrite.All* 
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
GET /groups
```
### Optional query parameters
This method supports the [OData Query Parameters](http://graph.microsoft.io/docs/overview/query_parameters) to help customize the response.
### Request headers
| Name       | Type | Description|
|:-----------|:------|:----------|
| Authorization  | string  | Bearer <token>. Required. |

### Request body
Do not supply a request body for this method.
### Response
If successful, this method returns a `200 OK` response code and collection of [group](../resources/group.md) objects in the response body.
### Example
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "get_groups"
}-->
```http
GET https://graph.microsoft.com/v1.0/groups
```
##### Response
Here is an example of the response. 

Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.group",
  "isCollection": true
} -->
```http
Content-type: application/json
Content-length: xxx

 {
  "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#groups",
  "value": [
    {
      "id": "id-value",
      "description": "description-value",
      "displayName": "displayName-value",
      "groupTypes": [
        "groupTypes-value"
      ],
      "mail": "mail-value",
      "mailEnabled": true,
      "mailNickname": "mailNickname-value",
      "onPremisesLastSyncDateTime": "onPremisesLastSyncDateTime-value",
      "onPremisesSecurityIdentifier": "onPremisesSecurityIdentifier-value",
      "onPremisesSyncEnabled": "onPremisesSyncEnabled-value",
      "proxyAddresses": [
        "proxyAddresses-value"
      ],
      "securityEnabled": "securityEnabled-value",
      "visibility": "visibility-value"
    },
    ...
  ]
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "List groups",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->