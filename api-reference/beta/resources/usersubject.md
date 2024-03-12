---
title: "userSubject resource type"
description: "**TODO: Add Description**"
author: "**TODO: Provide GitHub Name. See [topic-level metadata reference](https://aka.ms/msgo?pagePath=Document-APIs/Guidelines/Metadata)**"
ms.localizationpriority: medium
ms.subservice: "**TODO: Add MS prod. See [topic-level metadata reference](https://aka.ms/msgo?pagePath=Document-APIs/Guidelines/Metadata)**"
doc_type: resourcePageType
---

# userSubject resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

**TODO: Add Description**


Inherits from [conditionalAccessWhatIfSubject](../resources/conditionalaccesswhatifsubject.md).

## Properties
|Property|Type|Description|
|:---|:---|:---|
|externalTenantId|String|**TODO: Add Description**|
|externalUserType|conditionalAccessGuestOrExternalUserTypes|**TODO: Add Description**.The possible values are: `none`, `internalGuest`, `b2bCollaborationGuest`, `b2bCollaborationMember`, `b2bDirectConnectUser`, `otherExternalUser`, `serviceProvider`, `unknownFutureValue`.|
|userId|String|**TODO: Add Description**|

## Relationships
None.

## JSON representation
The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.userSubject"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.userSubject",
  "userId": "String",
  "externalTenantId": "String",
  "externalUserType": "String"
}
```

