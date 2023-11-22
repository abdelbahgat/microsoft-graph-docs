---
title: "privilegedAccessScheduleInstance resource type"
description: "An abstract type that exposes properties relating to the instances of membership and ownership assignments and eligibilities to groups governed by PIM."
author: "ilyalushnikov"
ms.localizationpriority: medium
ms.prod: "governance"
doc_type: resourcePageType
---

# privilegedAccessScheduleInstance resource type

Namespace: microsoft.graph

An abstract type that exposes properties relating to the instances of membership and ownership assignments and eligibilities to groups governed by PIM. This abstract type is inherited by the following derived types:
+ [privilegedAccessGroupAssignmentScheduleInstance](privilegedaccessgroupassignmentscheduleinstance.md)
+ [privilegedAccessGroupEligibilityScheduleInstance](privilegedaccessgroupeligibilityscheduleinstance.md)

Inherits from [entity](../resources/entity.md).

## Methods
None.

## Properties
|Property|Type|Description|
|:---|:---|:---|
|endDateTime|DateTimeOffset|When the schedule instance ends, and is required.|
|id|String|The identifier of the access assignment schedule instance, and is required. Inherited from [entity](../resources/entity.md).|
|startDateTime|DateTimeOffset|When this instance starts, and is required.|

## Relationships
None.

## JSON representation
Here's a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.privilegedAccessScheduleInstance",
  "baseType": "microsoft.graph.entity",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.privilegedAccessScheduleInstance",
  "id": "String (identifier)",
  "startDateTime": "String (timestamp)",
  "endDateTime": "String (timestamp)"
}
```

