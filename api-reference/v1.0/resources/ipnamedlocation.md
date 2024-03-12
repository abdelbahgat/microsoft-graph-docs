---
title: "ipNamedLocation resource type"
description: "Represents an Azure Active Directory named location defined by IP ranges. Named locations are custom rules that define network locations which can then be used in a Conditional Access policy."
ms.localizationpriority: medium
author: "davidspooner"
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
---

# ipNamedLocation resource type

Namespace: microsoft.graph

Represents an Azure Active Directory named location defined by IP ranges. Named locations are custom rules that define network locations which can then be used in a Conditional Access policy.

Inherits from [namedLocation](../resources/namedLocation.md)

## Methods

| Method       | Return Type | Description |
|:-------------|:------------|:------------|
| [List ipNamedLocations](../api/conditionalaccessroot-list-namedlocations.md) | [ipNamedLocation](ipNamedLocation.md) collection | Get all the **ipNamedLocation** objects in the organization. |
| [Create ipNamedLocation](../api/conditionalaccessroot-post-namedlocations.md) | [ipNamedLocation](ipNamedLocation.md) | Create a new **ipNamedLocation** object. |
| [Get ipNamedLocation](../api/ipnamedlocation-get.md) | [ipNamedLocation](ipnamedlocation.md) | Read the properties and relationships of an **ipNamedLocation** object. |
| [Update ipNamedLocation](../api/ipnamedlocation-update.md) | [ipNamedLocation](ipnamedlocation.md) | Update an **ipNamedLocation** object. |
| [Delete ipNamedLocation](../api/ipnamedlocation-delete.md) | None | Delete an **ipNamedLocation** object. |

## Properties

| Property     | Type        | Description |
|:-------------|:------------|:------------|
|createdDateTime|DateTimeOffset|The Timestamp type represents creation date and time of the location using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`. Read-only. Inherited from [namedLocation](../resources/namedLocation.md).|
|displayName|String|Human-readable name of the location. Required.|
|id|String|Identifier of a namedLocation object. Read-only. Inherited from [namedLocation](../resources/namedLocation.md).|
|ipRanges|[ipRange](iprange.md) collection|List of IP address ranges in IPv4 CIDR format (e.g. 1.2.3.4/32) or any allowable IPv6 format from IETF RFC5969. Required.|
|isTrusted|Boolean|`true` if this location is explicitly trusted. Optional. Default value is `false`.|
|modifiedDateTime|DateTimeOffset|The Timestamp type represents last modified date and time of the location using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`. Read-only. Inherited from [namedLocation](../resources/namedLocation.md).|

## Relationships

None.

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.ipNamedLocation"
}-->

```json
{
  "createdDateTime": "String (timestamp)",
  "displayName": "String",
  "id": "String (identifier)",
  "ipRanges": [{"@odata.type": "microsoft.graph.ipRange"}],
  "isTrusted": true,
  "modifiedDateTime": "String (timestamp)"
}
```

## See also

+ [What is Conditional Access?](/azure/active-directory/conditional-access/overview)
+ [Using the location condition in a Conditional Access policy](/azure/active-directory/conditional-access/location-condition)


<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "ipNamedLocation resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

