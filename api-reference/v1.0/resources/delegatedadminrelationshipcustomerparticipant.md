---
title: "delegatedAdminRelationshipCustomerParticipant resource type"
description: "Represents identification details of a customer in a delegated admin relationship."
author: "koravvams"
ms.localizationpriority: medium
ms.prod: partner-customer-administration
doc_type: resourcePageType
---

# delegatedAdminRelationshipCustomerParticipant resource type

Namespace: microsoft.graph

Represents identification details of a customer in a delegated admin relationship.

## Properties
|Property|Type|Description|
|:---|:---|:---|
|displayName|String|The display name of the customer tenant as set by Microsoft Entra ID. Read-only|
|tenantId|String|The Microsoft Entra ID-assigned tenant ID of the customer tenant.|

## Relationships
None.

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.delegatedAdminRelationshipCustomerParticipant"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.delegatedAdminRelationshipCustomerParticipant",
  "tenantId": "String",
  "displayName": "String"
}
```
