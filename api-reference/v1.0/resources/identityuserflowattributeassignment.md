---
title: "identityUserFlowAttributeAssignment resource type"
description: "Represents how attributes are collected in an identity user flow."
author: "jkdouglas"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
---

# identityUserFlowAttributeAssignment resource type

Namespace: microsoft.graph

Represents how attributes are collected in an identity user flow. This allows customization options for collecting attributes within the user flow. You can have multiple identityUserFlowAttributeAssignments within a single user flow that creates the experience for providing the information required by the user to complete sign-up.

## Methods

|Method|Return type|Description|
|:---|:---|:---|
|[Get identityUserFlowAttributeAssignment](../api/identityuserflowattributeassignment-get.md)|[identityUserFlowAttributeAssignment](../resources/identityuserflowattributeassignment.md)|Read the properties and relationships of an identityUserFlowAttributeAssignment object.|
|[Update identityUserFlowAttributeAssignment](../api/identityuserflowattributeassignment-update.md)|None|Update the properties of an identityUserFlowAttributeAssignment object.|
|[Delete identityUserFlowAttributeAssignment](../api/identityuserflowattributeassignment-delete.md)|None|Delete a specific identityUserFlowAttributeAssignment object.|
|[getOrder](../api/identityuserflowattributeassignment-getorder.md)|[assignmentOrder](../resources/assignmentorder.md)|Gets the order of the identityUserFlowAttributes being collected within a user flow.|
|[setOrder](../api/identityuserflowattributeassignment-setorder.md)|None|Sets the order of the identityUserFlowAttributes being collected within a user flow.|

## Properties

|Property|Type|Description|
|:---|:---|:---|
|id|String|The identifier of the identityUserFlowAttributeAssignment. This identifier is immutable after it is created. This is a read-only property.|
|displayName|String|The display name of the identityUserFlowAttribute within a user flow.|
|isOptional|Boolean|Determines whether the identityUserFlowAttribute is optional. `true` means the user doesn't have to provide a value. `false` means the user cannot complete sign-up without providing a value.|
|requiresVerification|Boolean|Determines whether the identityUserFlowAttribute requires verification. This is only used for verifying the user's phone number or email address.|
|userAttributeValues|[userAttributeValuesItem](../resources/userattributevaluesitem.md) collection|The input options for the user flow attribute. Only applicable when the userInputType is `radioSingleSelect`, `dropdownSingleSelect`, or `checkboxMultiSelect`.|
|userInputType|identityUserFlowAttributeInputType|The input type of the user flow attribute. Possible values are: `textBox`, `dateTimeDropdown`, `radioSingleSelect`, `dropdownSingleSelect`, `emailBox`, `checkboxMultiSelect`.|

## Relationships

|Relationship|Type|Description|
|:---|:---|:---|
|userAttribute|[identityUserFlowAttribute](../resources/identityuserflowattribute.md)|The user attribute that you want to add to your user flow.|

## JSON representation

The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.identityUserFlowAttributeAssignment",
  "openType": false
}
-->

``` json
{
  "@odata.type": "#microsoft.graph.identityUserFlowAttributeAssignment",
  "id": "String (identifier)",
  "isOptional": "Boolean",
  "requiresVerification": "Boolean",
  "userInputType": "String",
  "userAttributeValues": [
    {
      "@odata.type": "microsoft.graph.userAttributeValuesItem"
    }
  ],
  "displayName": "String"
}
```
