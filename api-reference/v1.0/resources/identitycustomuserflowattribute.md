---
title: "identityCustomUserFlowAttribute resource type"
description: "Represents a custom user flow attribute in Microsoft Entra ID for workforce tenants, Microsoft Entra ID for customers tenants, and Azure AD B2C tenants that can be used in self-service sign-up user flows."
author: "nanguil"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
---

# identityCustomUserFlowAttribute resource type

Namespace: microsoft.graph

Represents a custom user flow attribute in Microsoft Entra ID for workforce tenants, Microsoft Entra ID for customers tenants, and Azure AD B2C tenants that can be used in self-service sign-up user flows.

Inherits from [identityUserFlowAttribute](../resources/identityuserflowattribute.md).

## Properties

|Property|Type|Description|
|:---|:---|:---|
|dataType|identityUserFlowAttributeDataType|The data type of the user flow attribute, and can't be modified after the custom user flow attribute is created. The supported values for **dataType** are: `string` , `boolean` , `int64` , `stringCollection` , `dateTime`. Inherited from [identityUserFlowAttribute](../resources/identityuserflowattribute.md).|
|description|String|The description of the user flow attribute that's shown to the user at the time of sign-up. Inherited from [identityUserFlowAttribute](../resources/identityuserflowattribute.md)|
|displayName|String|The display name of the user flow attribute. Inherited from [identityUserFlowAttribute](../resources/identityuserflowattribute.md)|
|id|String|The identifier of the user flow attribute. This is a read-only attribute that is automatically created. Inherited from [identityUserFlowAttribute](../resources/identityuserflowattribute.md)|
|userFlowAttributeType|identityUserFlowAttributeType|The type of the user flow attribute and is a read-only attribute that is automatically set. The value for this property is `custom`. Inherited from [identityUserFlowAttribute](../resources/identityuserflowattribute.md).|


## Relationships

None.

## JSON representation

Here's a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.identityCustomUserFlowAttribute",
  "baseType": "microsoft.graph.identityUserFlowAttribute",
  "openType": false
}
-->

``` json
{
  "@odata.type": "#microsoft.graph.identityCustomUserFlowAttribute",
  "id": "String (identifier)",
  "displayName": "String",
  "description": "String",
  "userFlowAttributeType": "String",
  "dataType": "String"
}
```
