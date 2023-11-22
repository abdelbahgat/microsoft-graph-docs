---
title: "managedTenantGenericError resource type"
description: "Represents a generic error for a managed tenant."
author: "idwilliams"
ms.localizationpriority: medium
ms.prod: "multi-tenant-management"
doc_type: resourcePageType
---

# managedTenantGenericError resource type

Namespace: microsoft.graph.managedTenants

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a generic error for a managed tenant.

Inherits from [managedTenantOperationError](../resources/managedtenants-managedtenantoperationerror.md).

## Properties
|Property|Type|Description|
|:---|:---|:---|
|error|String|The error message for the exception. Inherited from [managedTenantOperationError](../resources/managedtenants-managedtenantoperationerror.md). Required. Read-only.|
|tenantId|String|The Microsoft Entra tenant identifier for the managed tenant. Inherited from [managedTenantOperationError](../resources/managedtenants-managedtenantoperationerror.md). Optional. Read-only.|

## Relationships
None.

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.managedTenants.managedTenantGenericError"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.managedTenants.managedTenantGenericError",
  "tenantId": "String",
  "error": "String"
}
```
