# Update person

Update the properties of a person object.
### Prerequisites
The following **scopes** are required to execute this API: *People.ReadWrite*
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
PATCH /me/people/<id>
PATCH /users/<id>/people/<id>
PATCH /drive/root/createdByUser/people/<id>
```
### Optional request headers
| Name       | Description|
|:-----------|:-----------|
| Authorization  | Bearer <code>|
| Workbook-Session-Id  | Workbook session Id that determines if changes are persisted or not. Optional.|

### Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|birthday|string|The person's birthday.|
|companyName|string|The name of the person's company.|
|department|string|The person's department.|
|displayName|string|The person's display name.|
|emailAddresses|[rankedEmailAddress](rankedemailaddress.md) collection|The person's email addresses.|
|givenName|string|The person's given name.|
|isFavorite|boolean|`true` if the user has flagged this person as a favorite.|
|mailboxType|string|The type of mailbox that is represented by the person's email address.|
|officeLocation|string|The location of the person's office.|
|personNotes|string|Free-form notes that the the user has taken about this person.|
|personType|string|The type of person, for example distribution list.|
|phones|[phone](phone.md) collection|The person's phone numbers.|
|postalAddresses|[location](location.md) collection|The person's addresses.|
|profession|string|The person's profession.|
|sources|[personDataSource](persondatasource.md) collection|The sources the user data comes from, for example Directory or Outlook Contacts.|
|surname|string|The person's surname.|
|title|string|The person's title.|
|webSites|[webSite](website.md) collection|The person's websites.|
|yomiCompany|string|The phonetic Japanese name of the person's company.|

### Response
If successful, this method returns a `200 OK` response code and updated [person](../resources/person.md) object in the response body.
### Example
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "update_person"
}-->
```http
PATCH https://graph.microsoft.com/v1.0/me/people/<id>
Content-type: application/json
Content-length: 196

{
  "displayName": "displayName-value",
  "givenName": "givenName-value",
  "surname": "surname-value",
  "birthday": "birthday-value",
  "personNotes": "personNotes-value",
  "isFavorite": true
}
```
##### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.person"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 196

{
  "displayName": "displayName-value",
  "givenName": "givenName-value",
  "surname": "surname-value",
  "birthday": "birthday-value",
  "personNotes": "personNotes-value",
  "isFavorite": true
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Update person",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->