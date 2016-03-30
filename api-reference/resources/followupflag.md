# followupFlag resource type

Represents properties of the follow up flag of an item, such as a message or contact.

### JSON representation

Here is a JSON representation of the resource

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.followupFlag"
}-->

```json
{
  "completedDateTime": {"@odata.type": "microsoft.graph.datetimetimezone"},
  "dueDateTime": {"@odata.type": "microsoft.graph.datetimetimezone"},
  "startDateTime": {"@odata.type": "microsoft.graph.datetimetimezone"},
  "flagStatus": "String"
}

```
### Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|completedDateTime|[DateTimeTimeZone](datetimetimezone.md)|The complete date of the item.|
|dueDateTime|[DateTimeTimeZone](datetimetimezone.md)|The due date of the item.|
|startDateTime|[DateTimeTimeZone](datetimetimezone.md)|The start date of the item.|
|flagStatus|String|The flag status of the item. Possible values are `NotFlagged`, `Completed` and `Flagged`.|

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "followupFlag resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->