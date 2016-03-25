# multiValueLegacyExtendedProperty resource type

An extended property that can contain a collection of multiple values.


### Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[Get multiValueLegacyExtendedProperty](../api/multivaluelegacyextendedproperty_get.md) | [multiValueLegacyExtendedProperty](multivaluelegacyextendedproperty.md) |Read properties and relationships of multiValueLegacyExtendedProperty object.|


### Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|propertyId|string|The property ID used to identify the property. Read-only.|
|value|string collection|A collection of property values.|

### Relationships
None


### JSON representation

Here is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.multivaluelegacyextendedproperty"
}-->

```json
{
  "propertyId": "string (identifier)",
  "value": ["string"]
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "multiValueLegacyExtendedProperty resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->